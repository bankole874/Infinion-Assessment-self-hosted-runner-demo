# 🧑‍💻 Infinion-Assessment-self-hosted-runner-demo


## 🚀 Overview

This project demonstrates how to set up a **self-hosted GitHub Actions runner** on a local machine and run a test CI pipeline.

---

## 🧩 Steps Followed

1. Created a GitHub repository **Infinion-Assessment-self-hosted-runner-demo**.
2. Configured a self-hosted runner on my local PC using the GitHub-provided token.
- Runner on Local Setup
  
  <img width="956" height="963" alt="image" src="https://github.com/user-attachments/assets/d1d06d79-643c-41d7-97e4-ae4d75093ab9" />

- Runner active on Github
  
  <img width="928" height="570" alt="image" src="https://github.com/user-attachments/assets/6f607353-3623-49f5-b7f5-56fd79a94305" />

3. Created a simple workflow (`test.yml`) that executes on my self-hosted runner.
4. Successfully ran a test CI workflow that printed system info using the self-hosted runner.
5. Verified successful execution in the Actions tab.

---

## ⚙️ Challenges & Solutions

| Challenge                              | Solution                                                                     |
| -------------------------------------- | ---------------------------------------------------------------------------- |
| Workflow failed due to node not found. | Installed nodejs and npm `sudo apt update && sudo apt install -y nodejs npm` |
| Permission errors                      | Ran the terminal with admin/root privileges                               |
| Workflow not triggering                | Ensured correct branch trigger (`on: push to main`) |

### Challenge: Workflow failed due to node not found
- Run on host server:
  ```
  sudo apt update
  sudo apt install -y nodejs npm
  ```

<img width="920" height="885" alt="image" src="https://github.com/user-attachments/assets/a4ffdf9d-0e01-4256-bafd-caa2338882be" />

## Solution: Workflow successful on installing nodejs and npm

<img width="920" height="740" alt="image" src="https://github.com/user-attachments/assets/118f7d0e-17a4-4028-bb11-7c303cdc64bf" />

---

## 🧠 Production Considerations

* Use **dedicated VMs or containers** (not personal machines).
* Implement **auto-scaling runners** (e.g., via GitHub Actions Runner Controller on Kubernetes).
* Monitor runner health with logging and alerting.
* Run runners in **isolated networks** to prevent access leaks.

---

## 🔐 Security Considerations

* Make Repos private for secured access.
* Stored tokens as **GitHub secrets**, not in plain text.
* Restricted runner scope to specific repositories.
* Regularly **rotate GitHub runner tokens**.
* Used **least privilege principle** for system permissions.
* Enabled **firewall and antivirus** on the host machine.

---

## 🙂 Thank You

