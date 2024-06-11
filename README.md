<h1>Programowanie fullstack w chmurze obliczeniowej - Projekt</h1>
<h2>Autor: Michał Moń, I2N 2.3</h2>
<h3>Skrócony opis projektu</h3>
<p>Przy użyciu <b>GitHub Actions</b> oraz <b>ArgoCD</b> został stworzony pipeline CI/CD, który po dokonaniu zmian w repozytorium na platformie GitHub uruchamia przepływ, który buduje obraz z <b>pliku Dockerfile</b>. Obraz ten przesyłany jest na platformę <b>DockerHub</b>, skąd <b>ArgoCD</b> „sczytuje” i uaktualnia zasoby działające na <b>klastrze Kubernetes</b>. Dodatkowo w projekcie wykorzystano <b>Ingress</b> oraz <b>cert-manager</b>.</br></p>
<h4>Opis repozytorium:</h4>
<ul>
  <li><b>.github/workflows</b> – katalog z przepływem GitHub Actions</li>
  <li><b>cert-manager</b> – (źródło: https://cert-manager.io/docs/installation/) z jego pomocą została utworzona infrastruktura PKI, po czym utworzone CA zostało dodane do zaufanych w przeglądarce. Zadaniem <b>cert-manager</b> jest zarządzanie certyfikatami w klastrze na potrzeby usług uruchamianych w ramach tego projektu. W środku katalogu znajdują się dwa pliki .yaml, przy użyciu których ArgoCD uruchamia potrzebne zasoby.</li>
  <li><b>src</b> – katalog z <b>kodem źródłowym aplikacji</b> oraz <b>plikiem Dockerfile</b>, z którego budowany jest obraz przesyłany na platformę <b>DockerHub</b> w celu późniejszego wykorzystania (źródło: https://github.com/kubernetes/examples/tree/master/guestbook). Plik <b>Dockerfile</b> został zmodyfikowany względem oryginalnego, tak aby działał poprawnie przy wykorzystaniu GitHub Actions.</li>
  <li><b>test-app-deployment</b> – katalog z plikami .yaml tworzącymi <b>Deployment i Service frontendu oraz backendu</b> (bazy danych Redis) aplikacji wykorzystanej w projekcie (źródło: j.w.). Dodatkowo został dodany plik <b>ingress-frontend.yaml</b>, aby uzyskać dostęp do aplikacji przez przeglądarkę internetową (oraz w celu poprawnego działania certyfikatu).</li>
</ul>
