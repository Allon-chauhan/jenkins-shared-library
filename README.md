# 📦 Creating a Jenkins Shared Library

## 🛠 Technologies Used:
1. **Jenkins** 🏗️
2. **Groovy** 📜
3. **Docker** 🐳
4. **Git** 🔗
5. **Java** ☕
6. **Maven** 🔧

---

## ✅ Prerequisites:
We will be creating this using an existing **[Jenkins multi-branch pipeline](https://github.com/Allon-chauhan/jenkins-cipipeline.git)**.

---

## 📂 Creating a Groovy Project
1. **Set up a new Groovy project** in a directory.
2. Create a new directory in the project called **`vars`**.
3. Separate functions from the **Jenkins multi-branch pipeline’s Groovy script**.
4. In this case, we are separating **two functions**:
    - `buildApp.groovy`
    - `imageApp.groovy`

These functions will be called inside the **Jenkinsfile**.

---

## 📤 Creating a Jenkins Shared Library Repository
1. **Create a new Git repository**.
2. Push the Groovy project to this repository.

---

## ⚙️ Configuring Jenkins Shared Library in Jenkins Server
1. **Go to Manage Jenkins settings**.
2. Scroll down to **Global Trusted Pipeline Libraries**.
3. **Provide a custom name** for the library.
4. **Select `Modern SCM`** as the retrieval method.
5. **Set the SCM to Git** and provide:
    - The **repository URL**.
    - The **authentication credentials**.

---

## 📝 Modifying the Jenkinsfile
1. Using a **multi-branch pipeline**, create a new branch named **`jenkins-shared-lib`**.
2. Add the following line to your **Jenkinsfile**:
   ```groovy
   @Library('jenkins-shared-library') _
   ```
3. Modify **two pipeline stages** (`build jar` & `build image`) to call functions from the shared library.
4. Remove those two functions from the Groovy script to keep things clean.

---

🚀 **Now you’re all set! You can initiate a build using the shared library.** 🎉
