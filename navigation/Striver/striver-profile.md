---
layout: base
title: Striver Profile
search_exclude: true
permalink: /Striver/striver-profile
author: Hithin, Nikith, Rayhaan, Pradyun, Neil, Kush, Zaid
---

<div class="sidebar">
    <a href="/flocker_frontend/Striver/striver-achievements" class="sidebar-btn">⭐️ Achievements</a>
    <a href="/flocker_frontend/Striver/striver-challenges" class="sidebar-btn">📉 Challenges</a>
    <a href="/flocker_frontend/Striver/striver-ai" class="sidebar-btn">🤖 AI</a>
    <a href="/flocker_frontend/Striver/striver-about" class="sidebar-btn">❓ About</a>
    <a href="/flocker_frontend/Striver/striver-terms" class="sidebar-btn">📄 Terms</a>
    <a href="/flocker_frontend/Striver/striver-profile" class="sidebar-btn"> Profile</a>
</div>

<style>
    .sidebar {
        position: fixed;
        top: 0;
        left: 0;
        width: 150px;
        height: 100%;
        background-color: #121212 !important;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-top: 20px;
        color: white;
        border-right: 1px solid gray;
    }
    .sidebar-btn {
        background-color: #121212;
        color: white !important;
        border: 2px solid gray;
        margin: 10px 0;
        padding: 10px;
        border-radius: 8px;
        font-size: 16px;
        width: 120px;
        text-align: center;
        cursor: pointer;
        text-decoration: none;
    }
</style>
<div class="profile-container">
 <div class="card">
   <form>
     <div>
       <label for="newUid">Enter New Username:</label>
       <input type="text" id="newUid" placeholder="Username">
     </div>
     <div>
       <label for="newName">Enter New Display Name:</label>
       <input type="text" id="newName" placeholder="New Name">
     </div>
      <div>
       <label for="newAboutMe">Change Your About Me:</label>
       <input type="text" id="newAboutMe" placeholder="About me">
     </div>
     <br>
     <br>
     <label for="profilePicture" class="file-icon"> Upload Profile Picture <i class="fas fa-upload"></i>
     </label>
     <input type="file" id="profilePicture" accept="image/*" onchange="saveProfilePicture()">
     <div class="image-container" id="profileImageBox">
     </div>
     <p id="profile-message" style="color: red;"></p>
   </form>
 </div>
</div>

<script type="module">

import {pythonURI, fetchOptions } from '{{site.baseurl}}/assets/js/api/config.js';

import { putUpdate, postUpdate, deleteData, logoutUser } from "{{site.baseurl}}/assets/js/api/profile.js";

function updateTableWithData(data) {
   const tableBody = document.getElementById('profileResult');
   tableBody.innerHTML = '';

   data.sections.forEach((section, index) => {
       const tr = document.createElement('tr');
       const themeCell = document.createElement('td');
       const nameCell = document.createElement('td');

       themeCell.textContent = section.theme;
       nameCell.textContent = section.name;

       const trashIcon = document.createElement('i');
       trashIcon.className = 'fas fa-trash-alt trash-icon';
       trashIcon.style.marginLeft = '10px';
       themeCell.appendChild(trashIcon);

       trashIcon.addEventListener('click', async function (event) {
           event.preventDefault();
           const URL = pythonURI + "/api/user/section";
           tr.remove();

           const options = {
               URL,
               body: { sections: [section.theme] },
               message: 'profile-message',
           };

           try {
               await deleteData(options);
           } catch (error) {
               console.error('Error deleting section:', error.message);
               document.getElementById('profile-message').textContent = 'Error deleting section: ' + error.message;
           }
       });

      yearCell.classList.add('editable'); 
      yearCell.innerHTML = `${section.year} <i class="fas fa-pencil-alt edit-icon" style="margin-left: 10px;"></i>`;

       
       yearCell.addEventListener('click', function () {
           const input = document.createElement('input');
           input.type = 'text';
           input.value = section.year;
           input.className = 'edit-input';
           yearCell.innerHTML = '';
           yearCell.appendChild(input);

           input.focus();

           input.addEventListener('blur', async function () {
               const newYear = input.value;
               const URL = pythonURI + "/api/user/section";
               const options = {
                   URL,
                   body: { section: { theme: section.theme, year: newYear } },
                   message: 'profile-message',
               };

               try {
                   await putUpdate(options);
               } catch (error) {
                   console.error('Error updating year:', error.message);
                   document.getElementById('profile-message').textContent = 'Error updating year: ' + error.message;
               }

               yearCell.textContent = newYear;
           });

           input.addEventListener('keydown', function (event) {
               if (event.key === 'Enter') {
                   input.blur();
               }
           });
       });
       tr.appendChild(themeCell);
       tr.appendChild(nameCell);

       tableBody.appendChild(tr);
   });

}


async function fetchUserProfile() {
    const URL = pythonURI + "/api/id/pfp"; 

    try {
        const response = await fetch(URL, fetchOptions);
        if (!response.ok) {
            throw new Error(`Failed to fetch user profile: ${response.status}`);
        }

        const profileData = await response.json();
        displayUserProfile(profileData);
    } catch (error) {
        console.error('Error fetching user profile:', error.message);
       
    }
}

function displayUserProfile(profileData) {
    const profileImageBox = document.getElementById('profileImageBox');
    if (profileData.pfp) {
        const img = document.createElement('img');
        img.src = `data:image/jpeg;base64,${profileData.pfp}`;
        img.alt = 'Profile Picture';
        profileImageBox.innerHTML = ''; 
        profileImageBox.appendChild(img); 
    } else {
        profileImageBox.innerHTML = '<p>No profile picture available.</p>';
    }

 
}

window.saveProfilePicture = async function () {

    const fileInput = document.getElementById('profilePicture');
    const file = fileInput.files[0];
    if (file) {
        const reader = new FileReader();
        reader.onload = function() {
            const profileImageBox = document.getElementById('profileImageBox');
            profileImageBox.innerHTML = `<img src="${reader.result}" alt="Profile Picture">`;
        };
        reader.readAsDataURL(file);
    }

    if (!file) return;

    try {
        const base64String = await convertToBase64(file);
        await sendProfilePicture(base64String);
        console.log('Profile picture uploaded successfully!');

    } catch (error) {
        console.error('Error uploading profile picture:', error.message);
      
    }
}


async function convertToBase64(file) {
    return new Promise((resolve, reject) => {
        const reader = new FileReader();
        reader.onload = () => resolve(reader.result.split(',')[1]); 
        reader.onerror = error => reject(error);
        reader.readAsDataURL(file);
    });
}


async function sendProfilePicture(base64String) {
   const URL = pythonURI + "/api/id/pfp";

   
   const options = {
       URL,
       body: { pfp: base64String },
       message: 'profile-message', 
       callback: () => {
           console.log('Profile picture uploaded successfully!');
      
       }
   };

   try {
       await putUpdate(options);
   } catch (error) {
       console.error('Error uploading new profile picture:', error.message);
       document.getElementById('profile-message').textContent = 'Error uploading new profile picture: ' + error.message;
   }
}
  
window.updateUidField = function(newUid) {
  const uidInput = document.getElementById('newUid');
  uidInput.value = newUid;
  uidInput.placeholder = newUid;
}

window.updateNameField = function(newName) {
  const nameInput = document.getElementById('newName');
  nameInput.value = newName;
  nameInput.placeholder = newName;
}


window.changeUid = async function(uid) {
   if (uid) {
       const URL = pythonURI + "/api/user";

       const options = {
           URL,
           body: { uid },
           message: 'uid-message', 
           callback: () => {
               alert("You updated your Github ID, so you will automatically be logged out. Be sure to remember your new github id to log in!");
               console.log('UID updated successfully!');
               window.updateUidField(uid);
               window.location.href = '/portfolio_2025/login'
           }
       };

       try {
           await putUpdate(options);
       } catch (error) {
           console.error('Error updating UID:', error.message);
           document.getElementById('uid-message').textContent = 'Error updating UID: ' + error.message;
       }
   }
}



window.changeName = async function(name) {
   if (name) {
       const URL = pythonURI + "/api/user";
       const options = {
           URL,
           body: { name },
           message: 'name-message',
           callback: () => {
               console.log('Name updated successfully!');
               window.updateNameField(name);
           }
       };
       try {
           await putUpdate(options);
       } catch (error) {
           console.error('Error updating Name:', error.message);
           document.getElementById('name-message').textContent = 'Error updating Name: ' + error.message;
       }
   }
}

document.getElementById('newUid').addEventListener('change', function() {
    const uid = this.value;
    window.changeUid(uid);

});


document.getElementById('newName').addEventListener('change', function() {
    const name = this.value;
    window.changeName(name);

});



window.fetchName = async function() {
    const URL = pythonURI + "/api/user"; 

    try {
        const response = await fetch(URL, fetchOptions);
        if (!response.ok) {
            throw new Error(`Failed to fetch Name: ${response.status}`);
        }

        const data = await response.json();
        return data.name;
    } catch (error) {
        console.error('Error fetching Name:', error.message);
        return null;
    }
};

window.setPlaceholders = async function() {
    const uidInput = document.getElementById('newUid');
    const nameInput = document.getElementById('newName');

    try {
        const uid = await window.fetchUid();
        const name = await window.fetchName();

        if (uid !== null) {
            uidInput.placeholder = uid;
        }
        if (name !== null) {
            nameInput.placeholder = name;
        }
    } catch (error) {
        console.error('Error setting placeholders:', error.message);
    }
};

document.addEventListener('DOMContentLoaded', async function () {
    try {
        await fetchUserProfile(); 
        await setPlaceholders();
    } catch (error) {
        console.error('Initialization error:', error.message);
   
    }
});f

</script>

