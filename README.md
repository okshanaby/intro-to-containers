# Complete Intro to Containers v2 — Notes & Projects

My notes and hands-on projects from the [**Complete Intro to Containers, v2**](https://frontendmasters.com/courses/complete-intro-containers-v2/) course by [Brian Holt](https://www.linkedin.com/in/btholt/) (working at **Microsoft** at the time of recording) on Frontend Masters.

It walks from first principles — building a "container" by hand with `chroot`, namespaces, and cgroups — all the way up to Docker, tiny production images, and orchestrating multi-container apps with Docker Compose and Kubernetes.

- 📚 **Course:** https://frontendmasters.com/courses/complete-intro-containers-v2/
- 📝 **Official notes:** https://containers-v2.holt.courses/
- 👤 **My learning profile:** https://frontendmasters.com/u/okshanaby/

---

## What's inside

Each numbered folder is one section of the course. The `.md` files are my written notes; the subfolders are the working projects built along the way.

| Section | Topic | Highlights |
| --- | --- | --- |
| **2. Crafting Containers by Hand** | The primitives behind containers | `chroot`, namespaces, cgroups, limiting resources |
| **3. Docker** | Docker fundamentals | Images, running JavaScript, tags, the Docker CLI |
| **4. Dockerfiles** | Writing Dockerfiles | Building a Node.js app, organizing files, dependencies, layers |
| **5. Making Tiny Containers** | Shrinking images | Alpine, custom Node Alpine images, multistage builds, distroless |
| **6. Docker Features** | Going further with Docker | Docker Scout, bind mounts, volumes, dev containers, networking |
| **7. Multi Container Projects** | Orchestration | Docker Compose, Kubernetes, Kompose, scaling |

### Project folders

- **`5. Making Tiny Containers/my-project`** — a minimal Node.js app used to practice multistage and distroless builds.
- **`6. Docker Features/docker-volume`** & **`node-mongo-app`** — exploring volumes, bind mounts, and container networking with a Node + MongoDB app.
- **`7. Multi Container Projects/docker-compose-project`** — a `web` + `api` app wired together with `docker-compose.yml`.
- **`7. Multi Container Projects/kubernetes-project`** — the same app expressed as Kubernetes Deployments and Services (`*-deployment.yaml`, `*-service.yaml`), with a Compose file converted via Kompose.
- **`project-files-for-complete-intro-to-containers-v2`** — the starter/reference files provided with the course (Alpine, Node.js apps, dev containers, etc.).

---

## Key concepts covered

- **Containers from scratch** — using `chroot` to jail a filesystem, namespaces to isolate processes/network, and cgroups to cap resources, to understand what Docker automates.
- **Images vs. containers** — an image is a packaged blueprint (filesystem + run instructions); a container is a running instance of it.
- **Dockerfiles & layers** — how each instruction creates a cached layer, and how to order them for fast rebuilds.
- **Tiny images** — Alpine base images, multistage builds, and distroless containers to ship the smallest, most secure artifact possible.
- **Docker features** — Docker Scout for vulnerability scanning, bind mounts vs. volumes for persistence, dev containers, and container networking.
- **Multi-container apps** — Docker Compose for local multi-service development, Kubernetes for orchestration, Kompose to translate Compose into K8s manifests, and how to scale replicas.

---

## Getting started

You'll need [Docker](https://docs.docker.com/get-docker/) installed. For the Kubernetes section, enable Kubernetes in Docker Desktop (or use a local cluster like [kind](https://kind.sigs.k8s.io/)/[minikube](https://minikube.sigs.k8s.io/)) plus [`kubectl`](https://kubernetes.io/docs/tasks/tools/).

```sh
# Clone
git clone <this-repo-url>
cd intro-to-containers

# Example: run the Docker Compose project
cd "7. Multi Container Projects/docker-compose-project"
docker compose up --build

# Example: deploy the Kubernetes project
cd "../kubernetes-project"
kubectl apply -f .
kubectl get pods
```

> The notes are best read top to bottom, section by section — they build on each other.

---

## Acknowledgements

All credit for the course material goes to **Brian Holt** and **Frontend Masters**. This repository is my personal study log while taking the course.
