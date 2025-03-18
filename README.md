# MLxDevOps-Notebook
Documenting my learnings 
# 🚀 Setting Up Jenkins on Docker: My Hands-On Journey

Hey there! 👋 Welcome to my Jenkins adventure! Today, I’m diving into **Jenkins on Docker**, setting it up from scratch, and sharing every step of the way. If you're a DevOps enthusiast, a recruiter checking out my skills, or a CTO looking for talent—this one's for you! 😉

---

## 🌟 Why Follow the Official Documentation?

Let's be real—when you're dealing with a tool as powerful as **Jenkins**, the last thing you want is a broken setup. That's why **I always follow the official documentation**:

✅ **Security First**: Avoid unnecessary vulnerabilities. 🛡️  
✅ **Stability Guaranteed**: No random errors from outdated guides. 💪  
✅ **Best Practices**: Learn it the right way from the source. 🎯  
✅ **Future-Proof**: Stay up to date with the latest updates. 🚀  

🔗 **Official Docs:** [Jenkins Docker Installation](https://www.jenkins.io/doc/book/installing/docker/)

---

## 🎬 Step 1: Creating a Docker Network for Jenkins

First things first—we need a dedicated Docker network for Jenkins. This helps with container communication and avoids unnecessary issues later. Let’s set it up:

```sh
$ docker network create jenkins
```

Simple, right? Now, on to the fun part! 😃

---

## 🚀 Step 2: Running Jenkins in a Docker Container

Now, let's **pull and run Jenkins** inside a container. This command will:
- **Run Jenkins in detached mode** (`-d`)
- **Map ports** so you can access it in the browser
- **Persist data** to keep configurations safe

```sh
$ docker run -d \
  --name jenkins \
  --network jenkins \
  -p 8080:8080 \
  -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  jenkins/jenkins:lts
```

Boom! 🎉 Jenkins is now running on `http://localhost:8080`. But wait—we need to unlock it first!

---

## 🔑 Step 3: Unlocking Jenkins

Jenkins requires an **initial admin password** to get started. Here’s how to find it:

1️⃣ **Jump into the Jenkins container:**

```sh
$ docker exec -it  <container_id> sh
```

2️⃣ **Retrieve the initial password:**

```sh
$ cat /var/jenkins_home/secrets/initialAdminPassword
```

3️⃣ **Copy that password**, head over to `http://localhost:8080`, and paste it in.  

🎉 **Congrats! Jenkins is now unlocked and ready to roll!**

---

## 🎯 What’s Next?

✅ Install recommended plugins  
✅ Set up your first pipeline  
✅ Integrate Jenkins with GitHub & Docker  

Stay tuned as I dive deeper into **CI/CD pipelines, automation, and DevOps magic!** 🤖✨

---

📢 **Follow my DevOps & ML journey:** [GitHub Profile](https://github.com/mldev850)  
Let’s build some cool stuff together! 🚀
