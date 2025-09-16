# Prerequisites - Getting Started (Minimal)

So you want to jump into Kubernetes but don’t want to be buried under 100 things?  
Here’s the bare minimum to start - no fluff, no deep theory.  

---

## 1. Linux Essentials (Quick)

Kubernetes runs on Linux-based nodes, so a tiny bit of Linux knowledge helps.

- **Where am I?**
  ```bash
  pwd     # show current path
  ls      # list files
  cd dir  # move into directory
  ```

- **Files & Folders**
  ```bash
  touch file.txt      # create file
  mkdir myfolder      # create folder
  rm file.txt         # remove file
  cat file.txt        # view file content
  ```

- **Permissions (only what you need now)**
  ```bash
  chmod +x script.sh   # make file executable
  ```

---

## 2. Docker Basics (Very Quick)

Kubernetes orchestrates containers, so knowing what a container is… kinda needed.

- **Container vs VM in one line:**  
  VM = heavy (OS + app)  
  Container = lightweight (just the app)

- **Install Docker:** [Official Docs](https://docs.docker.com/get-docker/)

- **Run your first container**
  ```bash
  docker run -d -p 8080:80 nginx
  ```
  Open your browser → `http://localhost:8080` → *nginx is live.*

---

## 3. YAML Basics

Kubernetes configs use YAML, so we need to know:

- Indentation matters (spaces, not tabs!)
- Key → Value
- Lists

Example:
```yaml
name: hussain
skills:
  - docker
  - kubernetes
```

---

## That’s it!

You already have enough to start with Kubernetes.  
Don’t overthink. Spin up your first cluster and learn on the go.  
We’ll pick up extra stuff when we actually need it.
