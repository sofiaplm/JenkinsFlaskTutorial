# 🚀 Flask Docker CI/CD Pipeline with Jenkins

Αυτό το repository περιέχει μια απλή εφαρμογή Python Flask, η οποία "πακετάρεται" σε Docker Container και γίνεται deploy αυτόματα μέσω ενός Jenkins Pipeline.

Σκοπός του project είναι η επίδειξη μιας ολοκληρωμένης ροής **CI/CD (Continuous Integration / Continuous Deployment)** σε τοπικό περιβάλλον (Local macOS).

---

## 🛠️ Τεχνολογίες που χρησιμοποιήθηκαν

* **Python (Flask):** Για τη δημιουργία του Web API.
* **Docker:** Για την κοντεινεροποίηση (containerization) της εφαρμογής.
* **Jenkins:** Για την αυτοματοποίηση της διαδικασίας Build & Deploy (Pipeline).
* **Git & GitHub:** Για τον έλεγχο εκδόσεων (Version Control).

---

## 📂 Δομή Φακέλων

```text
├── app.py             # Ο κώδικας της εφαρμογής Flask
├── Dockerfile         # Οδηγίες για το χτίσιμο του Docker Image
├── Jenkinsfile        # Το σενάριο (script) για το Jenkins Pipeline
├── requirements.txt   # Οι βιβλιοθήκες Python που απαιτούνται
├── .gitignore         # Αρχεία που αγνοεί το Git (π.χ. venv)
└── README.md          # Οδηγίες χρήσης

Αν θέλετε να τρέξετε την εφαρμογή χωρίς το Jenkins, ακολουθήστε τα βήματα:

1. Build το Docker Image
docker build -t flask-api .

2. Εκκίνηση του Container
Τρέχουμε την εφαρμογή στο port 5001 (για αποφυγή conflicts στο macOS):
docker run -p 5001:5001 flask-api

3. Έλεγχος
Ανοίξτε τον browser στο: http://localhost:5001/

🤖 Ρύθμιση του Jenkins Pipeline
Το project περιλαμβάνει ένα Jenkinsfile που αυτοματοποιεί τη διαδικασία.

Βήματα στο Jenkins Dashboard:
Νέο Item: Δημιουργία νέου "Pipeline" project.

SCM: Επιλογή Git και εισαγωγή του URL του repository.

Branch: Ορισμός του branch σε */main.

Script Path: Jenkinsfile