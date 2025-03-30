# CloudVandana
# 1.Profile

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile Generator</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 2rem;
            min-height: 100vh;
        }
        
        .container {
            width: 100%;
            max-width: 1000px;
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }
        
        .profile-form {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }
        
        h1 {
            margin-bottom: 1.5rem;
            color: #333;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #555;
        }
        
        input, textarea, select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .color-picker {
            display: flex;
            gap: 1rem;
            align-items: center;
        }
        
        .color-preview {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 1px solid #ddd;
        }
        
        .form-row {
            display: flex;
            gap: 1rem;
            margin-bottom: 1rem;
        }
        
        .form-row .form-group {
            flex: 1;
            margin-bottom: 0;
        }
        
        button {
            background-color: #4a6cf7;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 5px;
            font-size: 1rem;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        
        button:hover {
            background-color: #3451c6;
        }
        
        .profile-card {
            background-color: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 4px 20px rgba(0,0,0,0.15);
            max-width: 400px;
            margin: 0 auto;
        }
        
        .profile-header {
            height: 120px;
            position: relative;
        }
        
        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            border: 5px solid white;
            position: absolute;
            bottom: -60px;
            left: 50%;
            transform: translateX(-50%);
            object-fit: cover;
            background-color: #f0f0f0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #aaa;
            font-size: 2rem;
        }
        
        .profile-img img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
        }
        
        .profile-body {
            padding: 80px 1.5rem 1.5rem;
            text-align: center;
        }
        
        .profile-name {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }
        
        .profile-title {
            color: #777;
            margin-bottom: 1rem;
        }
        
        .profile-bio {
            margin-bottom: 1.5rem;
            color: #444;
            line-height: 1.5;
        }
        
        .profile-social {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 1rem;
        }
        
        .social-icon {
            width: 36px;
            height: 36px;
            background-color: #f5f5f5;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s;
        }
        
        .social-icon:hover {
            transform: translateY(-3px);
        }
        
        .profile-contact {
            display: inline-block;
            padding: 8px 20px;
            border-radius: 50px;
            margin-top: 1rem;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.2s;
        }
        
        .profile-contact:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .preview-section {
            margin-top: 1rem;
            display: none;
        }
        
        .image-upload {
            position: relative;
            width: 150px;
            height: 150px;
            margin: 0 auto 1rem;
            border-radius: 50%;
            overflow: hidden;
            background-color: #f0f0f0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #aaa;
        }
        
        .image-upload input {
            position: absolute;
            width: 100%;
            height: 100%;
            opacity: 0;
            cursor: pointer;
        }
        
        .image-upload img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .upload-icon {
            font-size: 2rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="profile-form">
            <h1>Profile Generator</h1>
            <div class="form-row">
                <div class="form-group">
                    <label for="name">Full Name</label>
                    <input type="text" id="name" placeholder="Enter Name">
                </div>
                <div class="form-group">
                    <label for="title">Professional Title</label>
                    <input type="text" id="title" placeholder="Enter your Profession">
                </div>
            </div>
            
            <div class="form-group">
                <label for="bio">Bio</label>
                <textarea id="bio" rows="4" placeholder="Write a short bio about yourself..."></textarea>
            </div>
            
            <div class="form-group">
                <label>Profile Image</label>
                <div class="image-upload" id="imageUpload">
                    <input type="file" id="profileImg" accept="image/*">
                    <div class="upload-icon">+</div>
                </div>
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label for="headerColor">Header Color</label>
                    <div class="color-picker">
                        <input type="color" id="headerColor" value="#4a6cf7">
                        <div class="color-preview" id="headerColorPreview" style="background-color: #4a6cf7"></div>
                    </div>
                </div>
                <div class="form-group">
                    <label for="buttonColor">Button Color</label>
                    <div class="color-picker">
                        <input type="color" id="buttonColor" value="#4a6cf7">
                        <div class="color-preview" id="buttonColorPreview" style="background-color: #4a6cf7"></div>
                    </div>
                </div>
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" placeholder="youremail@example.com">
                </div>
                <div class="form-group">
                    <label for="contactText">Contact Button Text</label>
                    <input type="text" id="contactText" placeholder="Contact Me" value="Contact Me">
                </div>
            </div>
            
            <button id="generateBtn">Generate Profile</button>
            
            <div class="preview-section" id="previewSection">
                <h2 style="margin: 1.5rem 0 1rem;">Preview</h2>
                <div class="profile-card">
                    <div class="profile-header" id="profileHeader" style="background-color: #4a6cf7;">
                        <div class="profile-img" id="profileImgPreview">
                            <div class="upload-icon">+</div>
                        </div>
                    </div>
                    <div class="profile-body">
                        <div class="profile-name" id="profileName">John Doe</div>
                        <div class="profile-title" id="profileTitle">Web Developer</div>
                        <div class="profile-bio" id="profileBio">
                            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi aliquam, felis quis viverra tincidunt, erat ipsum.
                        </div>
                        <div class="profile-social">
                            <div class="social-icon">
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
                            </div>
                            <div class="social-icon">
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"></path></svg>
                            </div>
                            <div class="social-icon">
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line></svg>
                            </div>
                        </div>
                        <a href="#" class="profile-contact" id="profileContact" style="background-color: #4a6cf7; color: white;">
                            Contact Me
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const generateBtn = document.getElementById('generateBtn');
            const previewSection = document.getElementById('previewSection');
            const nameInput = document.getElementById('name');
            const titleInput = document.getElementById('title');
            const bioInput = document.getElementById('bio');
            const profileImgInput = document.getElementById('profileImg');
            const headerColorInput = document.getElementById('headerColor');
            const buttonColorInput = document.getElementById('buttonColor');
            const emailInput = document.getElementById('email');
            const contactTextInput = document.getElementById('contactText');
            const profileHeader = document.getElementById('profileHeader');
            const profileImgPreview = document.getElementById('profileImgPreview');
            const profileName = document.getElementById('profileName');
            const profileTitle = document.getElementById('profileTitle');
            const profileBio = document.getElementById('profileBio');
            const profileContact = document.getElementById('profileContact');
            const headerColorPreview = document.getElementById('headerColorPreview');
            const buttonColorPreview = document.getElementById('buttonColorPreview');
            headerColorInput.addEventListener('input', function() {
                headerColorPreview.style.backgroundColor = this.value;
            });
            
            buttonColorInput.addEventListener('input', function() {
                buttonColorPreview.style.backgroundColor = this.value;
            });
            profileImgInput.addEventListener('change', function() {
                const file = this.files[0];
                if (file) {
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        const img = document.createElement('img');
                        img.src = e.target.result;
                        profileImgPreview.innerHTML = '';
                        profileImgPreview.appendChild(img);
                        const uploadArea = document.getElementById('imageUpload');
                        uploadArea.innerHTML = `
                            <input type="file" id="profileImg" accept="image/*">
                            <img src="${e.target.result}" alt="Profile">
                        `;
                        document.getElementById('profileImg').addEventListener('change', arguments.callee);
                    };
                    reader.readAsDataURL(file);
                }
            });
            generateBtn.addEventListener('click', function() {
                profileName.textContent = nameInput.value || 'Enter Name';
                profileTitle.textContent = titleInput.value || 'Enter your Profession';
                profileBio.textContent = bioInput.value || 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi aliquam, felis quis viverra tincidunt, erat ipsum.';
                profileHeader.style.backgroundColor = headerColorInput.value;
                profileContact.style.backgroundColor = buttonColorInput.value;
                profileContact.textContent = contactTextInput.value || 'Contact Me';
                profileContact.href = emailInput.value ? `mailto:${emailInput.value}` : '#';
                previewSection.style.display = 'block';
                previewSection.scrollIntoView({ behavior: 'smooth' });
            });
        });
    </script>
</body>
</html>

# 2.Anagrams
import java.util.Arrays;
import java.util.Scanner;
public class AnagramChecker 
{
    public static boolean isAnagram(String str1, String str2) 
    {
        str1 = str1.replaceAll("\\s", "").toLowerCase();
        str2 = str2.replaceAll("\\s", "").toLowerCase();
        if (str1.length() != str2.length()) 
        {
            return false;
        }
        char[] arr1 = str1.toCharArray();
        char[] arr2 = str2.toCharArray();
        Arrays.sort(arr1);
        Arrays.sort(arr2);
        return Arrays.equals(arr1, arr2);
    }

    public static void main(String[] args) 
    {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter first string: ");
        String str1 = scanner.nextLine();
        System.out.print("Enter second string: ");
        String str2 = scanner.nextLine();
        if (isAnagram(str1, str2)) 
        {
            System.out.println("Output: true");
        } 
        else 
        {
            System.out.println("Output: false");
        }
        scanner.close();
    }
}
# 3.Empolyee Management(OOP'S)
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class Employee 
{
    private int id;
    private String name;
    private double salary;

    public Employee(int id, String name, double salary) 
    {
        this.id = id;
        this.name = name;
        this.salary = salary;
    }

    public void displayDetails() {
        System.out.println("Employee ID: " + id);
        System.out.println("Name: " + name);
        System.out.println("Salary: $" + salary);
        System.out.println("---------------------------");
    }
}

public class Main 
{
    public static void main(String[] args) 
    {
        List<Employee> employees = new ArrayList<>();
        employees.add(new Employee(101, "Alice", 50000));
        employees.add(new Employee(102, "Bob", 60000));
        employees.add(new Employee(103, "Charlie", 55000));
        System.out.println("Employee Details:");
        for (Employee emp : employees)
        {
            emp.displayDetails();
        }
    }
}
# To-Do list(JavaScript - DOM)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple To-Do List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #1a1a2e;
            flex-direction: column;
            color: #ffffff;
        }
        #todo-container {
            background: #0f3460;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 255, 255, 0.6);
            width: 300px;
            text-align: center;
        }
        input {
            width: 70%;
            padding: 8px;
            background: #16213e;
            color: #00ffff;
            border: 1px solid #00ffff;
            border-radius: 5px;
        }
        button {
            padding: 8px;
            margin-left: 5px;
            cursor: pointer;
            background: #e94560;
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: bold;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            display: flex;
            justify-content: space-between;
            background: #16213e;
            margin-top: 5px;
            padding: 5px;
            border-radius: 5px;
            color: #00ffff;
            border: 1px solid #00ffff;
        }
        .delete {
            background: #e94560;
            color: white;
            border: none;
            padding: 5px;
            cursor: pointer;
            border-radius: 5px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div id="todo-container">
        <h2>To-Do List</h2>
        <input type="text" id="taskInput" placeholder="Add a new task">
        <button onclick="addTask()">Add</button>
        <ul id="taskList"></ul>
    </div>

    <script>
        function addTask() {
            let taskInput = document.getElementById("taskInput");
            let taskText = taskInput.value.trim();
            if (taskText === "") return;

            let li = document.createElement("li");
            li.innerHTML = `${taskText} <button class='delete' onclick='removeTask(this)'>X</button>`;
            document.getElementById("taskList").appendChild(li);

            taskInput.value = "";
        }
        
        function removeTask(button) {
            button.parentElement.remove();
        }
    </script>
</body>
</html>

# Image Slider (DOM Manipulation)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Slider</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #1a1a2e;
            flex-direction: column;
        }
        #slider-container {
            position: relative;
            max-width: 100%;
            max-height: 100vh;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 255, 255, 0.6);
            display: flex;
            justify-content: center;
            align-items: center;
        }
        #slider {
            max-width: 100%;
            max-height: 100vh;
            object-fit: contain;
        }
        .btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: #e94560;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
            font-weight: bold;
        }
        #prev {
            left: 10px;
        }
        #next {
            right: 10px;
        }
    </style>
</head>
<body>
    <div id="slider-container">
        <img id="slider" src="C://Users//91994//Downloads//ART1.jpg" alt="Image Slider">
        <button id="prev" class="btn" onclick="prevImage()">Prev</button>
        <button id="next" class="btn" onclick="nextImage()">Next</button>
    </div>

    <script>
        const images = [
            "C://Users//91994//Downloads//ART1.jpg",
            "C://Users//91994//Downloads//ART2.jpg",
            "C://Users//91994//Downloads//ART3.jpg",
            "C://Users//91994//Downloads//ART4.jpg"
        ];

        let currentIndex = 0;
        const slider = document.getElementById("slider");

        function updateImage() {
            slider.src = images[currentIndex];
        }

        function prevImage() {
            currentIndex = (currentIndex === 0) ? images.length - 1 : currentIndex - 1;
            updateImage();
        }

        function nextImage() {
            currentIndex = (currentIndex === images.length - 1) ? 0 : currentIndex + 1;
            updateImage();
        }
    </script>
</body>
</html>
