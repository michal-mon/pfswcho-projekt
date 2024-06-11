<h1Programowanie fullstack w chmurze obliczeniowej - Projekt</h1>
<h2>Autor: Michał Moń, I2N 2.3</h2>
<h3>Skrócony opis projektu</h3>
<p>Przy użyciu <b>GitHub Actions</b> oraz <b>ArgoCD</b> został stworzony pipeline CI/CD, który po dokonaniu zmian w repozytorium na platformie GitHub uruchamia przepływ, który buduje obraz z <b>pliku Dockerfile</b>. Obraz ten przesyłany jest na platformę <b>DockerHub</b>, skąd <b>ArgoCD</b> „sczytuje” i uaktualnia zasoby działające na <b>klastrze Kubernetes</b>. Dodatkowo w projekcie wykorzystano <b>Ingress</b> oraz <b>cert-manager</b>.</br></p>
<h4>Opis repozytorium:</h4>
