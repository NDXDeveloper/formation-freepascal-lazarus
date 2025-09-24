# Formation FreePascal/Lazarus - Niveau Développeur Avancé
## Edition Multi-plateforme Windows/Ubuntu

## 1. [Introduction à FreePascal et Lazarus](01-introduction-freepascal-lazarus/README.md)

- 1.1 [Histoire et philosophie du projet FreePascal](01-introduction-freepascal-lazarus/01-histoire-philosophie-projet.md)
- 1.2 [L'écosystème Lazarus et son positionnement](01-introduction-freepascal-lazarus/02-ecosysteme-lazarus-positionnement.md)
- 1.3 [Différences avec Delphi et avantages du libre](01-introduction-freepascal-lazarus/03-differences-delphi-avantages-libre.md)
- 1.4 [Installation multi-plateforme](01-introduction-freepascal-lazarus/04-installation-multiplateforme.md)
  - 1.4.1 [Installation sur Windows (installer, chocolatey, portable)](01-introduction-freepascal-lazarus/04.1-installation-windows.md)
  - 1.4.2 [Installation sur Ubuntu (apt, snap, compilation source)](01-introduction-freepascal-lazarus/04.2-installation-ubuntu.md)
  - 1.4.3 [Installation sur macOS et BSD](01-introduction-freepascal-lazarus/04.3-installation-macos-bsd.md)
- 1.5 [Configuration avancée du compilateur FPC](01-introduction-freepascal-lazarus/05-configuration-avancee-compilateur-fpc.md)
- 1.6 [Modes de compatibilité (Turbo Pascal, Delphi, ObjFPC)](01-introduction-freepascal-lazarus/06-modes-compatibilite.md)
- 1.7 [Architecture du compilateur et processus de compilation](01-introduction-freepascal-lazarus/07-architecture-compilateur-processus-compilation.md)
- 1.8 [Configuration d'environnements de développement dual-boot/VM](01-introduction-freepascal-lazarus/08-configuration-environnements-dual-boot-vm.md)
- 1.9 [Contribution aux projets open source FreePascal/Lazarus](01-introduction-freepascal-lazarus/09-contribution-projets-open-source.md)

## 2. [Maîtrise de l'IDE Lazarus](02-maitrise-ide-lazarus/README.md)

- 2.1 [Architecture modulaire de l'IDE](02-maitrise-ide-lazarus/01-architecture-modulaire-ide.md)
- 2.2 [Configuration et personnalisation avancée](02-maitrise-ide-lazarus/02-configuration-personnalisation-avancee.md)
- 2.3 [Création et gestion de packages](02-maitrise-ide-lazarus/03-creation-gestion-packages.md)
- 2.4 [Outils de refactoring intégrés](02-maitrise-ide-lazarus/04-outils-refactoring-integres.md)
- 2.5 [Débogueur GDB et alternatives](02-maitrise-ide-lazarus/05-debogueur-gdb-alternatives.md)
  - 2.5.1 [Configuration GDB sur Windows](02-maitrise-ide-lazarus/05.1-configuration-gdb-windows.md)
  - 2.5.2 [Configuration GDB sur Ubuntu](02-maitrise-ide-lazarus/05.2-configuration-gdb-ubuntu.md)
  - 2.5.3 [Alternatives (LLDB, FpDebug)](02-maitrise-ide-lazarus/05.3-alternatives-lldb-fpdebug.md)
- 2.6 [Intégration avec les systèmes de contrôle de version](02-maitrise-ide-lazarus/06-integration-controle-version.md)
- 2.7 [Développement de plugins IDE](02-maitrise-ide-lazarus/07-developpement-plugins-ide.md)
- 2.8 [Cross-compilation Windows↔Linux](02-maitrise-ide-lazarus/08-cross-compilation-windows-linux.md)
- 2.9 [Profils de projet et configurations multiples](02-maitrise-ide-lazarus/09-profils-projet-configurations-multiples.md)
- 2.10 [Automatisation avec lazbuild](02-maitrise-ide-lazarus/10-automatisation-lazbuild.md)
- 2.11 [Synchronisation de projets entre OS](02-maitrise-ide-lazarus/11-synchronisation-projets-entre-os.md)

## 3. [Langage Object Pascal Avancé](03-langage-object-pascal-avance/README.md)

- 3.1 [Spécificités FreePascal vs Delphi](03-langage-object-pascal-avance/01-specificites-freepascal-vs-delphi.md)
- 3.2 [Généricité avancée et spécialisation](03-langage-object-pascal-avance/02-genericite-avancee-specialisation.md)
- 3.3 [Types avancés et RTTI (Run-Time Type Information)](03-langage-object-pascal-avance/03-types-avances-rtti.md)
- 3.4 [Programmation méta avec les attributs](03-langage-object-pascal-avance/04-programmation-meta-attributs.md)
- 3.5 [Gestion mémoire et comptage de références](03-langage-object-pascal-avance/05-gestion-memoire-comptage-references.md)
- 3.6 [Inline assembler multi-architecture (x86, x64, ARM)](03-langage-object-pascal-avance/06-inline-assembler-multi-architecture.md)
- 3.7 [Helpers de classe et de record](03-langage-object-pascal-avance/07-helpers-classe-record.md)
- 3.8 [Opérateurs avancés et surcharge](03-langage-object-pascal-avance/08-operateurs-avances-surcharge.md)
- 3.9 [Anonymous methods et closures](03-langage-object-pascal-avance/09-anonymous-methods-closures.md)
- 3.10 [Coroutines et programmation asynchrone](03-langage-object-pascal-avance/10-coroutines-programmation-asynchrone.md)
- 3.11 [Optimisations du compilateur](03-langage-object-pascal-avance/11-optimisations-compilateur.md)
- 3.12 [Directives de compilation conditionnelle multi-OS](03-langage-object-pascal-avance/12-directives-compilation-conditionnelle-multi-os.md)

## 4. [Framework LCL (Lazarus Component Library)](04-framework-lcl/README.md)

- 4.1 [Architecture de la LCL et widgetsets](04-framework-lcl/01-architecture-lcl-widgetsets.md)
- 4.2 [Composants visuels fondamentaux](04-framework-lcl/02-composants-visuels-fondamentaux.md)
- 4.3 [Composants non-visuels et services](04-framework-lcl/03-composants-non-visuels-services.md)
- 4.4 [Création de composants personnalisés portables](04-framework-lcl/04-creation-composants-personnalises-portables.md)
- 4.5 [Propriétés publiées et streaming](04-framework-lcl/05-proprietes-publiees-streaming.md)
- 4.6 [Éditeurs de propriétés personnalisés](04-framework-lcl/06-editeurs-proprietes-personnalises.md)
- 4.7 [Composants composites et frames](04-framework-lcl/07-composants-composites-frames.md)
- 4.8 [Gestion avancée des événements](04-framework-lcl/08-gestion-avancee-evenements.md)
- 4.9 [Thèmes et apparence personnalisée](04-framework-lcl/09-themes-apparence-personnalisee.md)
  - 4.9.1 [Thèmes Windows (styles visuels)](04-framework-lcl/09.1-themes-windows-styles-visuels.md)
  - 4.9.2 [Thèmes GTK/Qt sur Ubuntu](04-framework-lcl/09.2-themes-gtk-qt-ubuntu.md)
- 4.10 [Accessibilité et support des lecteurs d'écran](04-framework-lcl/10-accessibilite-support-lecteurs-ecran.md)
- 4.11 [High-DPI et mise à l'échelle](04-framework-lcl/11-high-dpi-mise-echelle.md)
- 4.12 [Gestion des différences d'interface OS](04-framework-lcl/12-gestion-differences-interface-os.md)

## 5. [Développement Multi-plateforme Approfondi](05-developpement-multiplateforme-approfondi/README.md)

- 5.1 [Abstraction des API systèmes](05-developpement-multiplateforme-approfondi/01-abstraction-api-systemes.md)
- 5.2 [Widgetsets détaillés](05-developpement-multiplateforme-approfondi/02-widgetsets-detailles.md)
  - 5.2.1 [Win32/Win64 pour Windows](05-developpement-multiplateforme-approfondi/02.1-win32-win64-windows.md)
  - 5.2.2 [GTK2/GTK3 pour Ubuntu/Linux](05-developpement-multiplateforme-approfondi/02.2-gtk2-gtk3-ubuntu-linux.md)
  - 5.2.3 [Qt5 comme alternative universelle](05-developpement-multiplateforme-approfondi/02.3-qt5-alternative-universelle.md)
  - 5.2.4 [Custom Drawn pour contrôle total](05-developpement-multiplateforme-approfondi/02.4-custom-drawn-controle-total.md)
- 5.3 [Gestion des différences plateforme](05-developpement-multiplateforme-approfondi/03-gestion-differences-plateforme.md)
  - 5.3.1 [Chemins et séparateurs](05-developpement-multiplateforme-approfondi/03.1-chemins-separateurs.md)
  - 5.3.2 [Fins de ligne (CRLF vs LF)](05-developpement-multiplateforme-approfondi/03.2-fins-ligne-crlf-vs-lf.md)
  - 5.3.3 [Encodages par défaut](05-developpement-multiplateforme-approfondi/03.3-encodages-defaut.md)
  - 5.3.4 [Sensibilité à la casse](05-developpement-multiplateforme-approfondi/03.4-sensibilite-casse.md)
- 5.4 [Compilation conditionnelle avancée](05-developpement-multiplateforme-approfondi/04-compilation-conditionnelle-avancee.md)
```pascal
{$IFDEF WINDOWS}
  // Code spécifique Windows
{$ENDIF}
{$IFDEF UNIX}
  {$IFDEF LINUX}
    // Code spécifique Linux/Ubuntu
  {$ENDIF}
{$ENDIF}
```
- 5.5 [Ressources et icônes multi-plateformes](05-developpement-multiplateforme-approfondi/05-ressources-icones-multiplatefomes.md)
- 5.6 [Tests cross-platform automatisés](05-developpement-multiplateforme-approfondi/06-tests-cross-platform-automatises.md)
- 5.7 [Intégration native par plateforme](05-developpement-multiplateforme-approfondi/07-integration-native-par-plateforme.md)
- 5.8 [Support ARM et architectures embarquées](05-developpement-multiplateforme-approfondi/08-support-arm-architectures-embarquees.md)
- 5.9 [Gestion unifiée de la configuration](05-developpement-multiplateforme-approfondi/09-gestion-unifiee-configuration.md)

## 6. Spécificités Windows

- 6.1 API Windows natives (WinAPI)
- 6.2 Services Windows
  - 6.2.1 Création de services
  - 6.2.2 Interaction avec le Service Control Manager
- 6.3 Registry Windows
  - 6.3.1 Lecture/écriture dans le registre
  - 6.3.2 Surveillance des modifications
- 6.4 COM/ActiveX et OLE
- 6.5 Windows Shell et intégration Explorer
- 6.6 UAC et élévation de privilèges
- 6.7 Signature Authenticode
- 6.8 Windows Installer (MSI)
- 6.9 PowerShell et scripts système
- 6.10 WMI (Windows Management Instrumentation)
- 6.11 DirectX et technologies multimédia Windows

## 7. Spécificités Linux/Ubuntu

- 7.1 Système de fichiers Linux et permissions
- 7.2 Services systemd
  - 7.2.1 Création d'unités systemd
  - 7.2.2 Journalctl et logging
- 7.3 D-Bus et communication inter-processus
- 7.4 Configuration via fichiers texte
- 7.5 Intégration desktop (GNOME/KDE/XFCE)
- 7.6 Freedesktop.org standards
- 7.7 Paquets DEB et PPA
- 7.8 AppImage et Flatpak
- 7.9 Scripts Bash et intégration shell
- 7.10 Signaux Unix et gestion des processus
- 7.11 X11 et Wayland
- 7.12 Politiques SELinux/AppArmor

## 8. Bases de Données et ORM Multi-plateformes

- 8.1 SQLdb : architecture et composants
- 8.2 Connexions natives identiques sur les deux OS
  - 8.2.1 PostgreSQL
  - 8.2.2 MySQL/MariaDB
  - 8.2.3 SQLite (embarqué)
  - 8.2.4 Firebird
- 8.3 Configuration des connexions par OS
  - 8.3.1 Chemins de bibliothèques Windows (.dll)
  - 8.3.2 Chemins de bibliothèques Linux (.so)
- 8.4 ZEOS DBO pour accès universel
- 8.5 Développement d'un ORM personnalisé portable
- 8.6 tiOPF - Framework de persistance objet
- 8.7 mORMot - SOA et ORM haute performance
- 8.8 Migration et versionnement de schémas
- 8.9 Optimisation des requêtes et indexation
- 8.10 Réplication et synchronisation
- 8.11 NoSQL avec MongoDB et Redis
- 8.12 GraphQL et API modernes

## 9. Programmation Web avec FreePascal

- 9.1 fpWeb - Framework web intégré
- 9.2 FastCGI et développement CGI
  - 9.2.1 Configuration IIS (Windows)
  - 9.2.2 Configuration Apache/Nginx (Ubuntu)
- 9.3 Brook Framework pour applications REST
- 9.4 WebSockets et Server-Sent Events
- 9.5 Templates et génération HTML
- 9.6 Sessions et authentification
- 9.7 Microservices avec FreePascal
- 9.8 Pas2JS - Transpilation vers JavaScript
- 9.9 WebAssembly avec FreePascal
- 9.10 Intégration avec frameworks JavaScript
- 9.11 Déploiement sur serveurs Windows/Linux

## 10. Programmation Réseau Avancée

- 10.1 Synapse - Bibliothèque réseau complète
- 10.2 Indy pour Lazarus
- 10.3 Protocoles TCP/UDP bas niveau
- 10.4 Serveurs HTTP/HTTPS personnalisés
- 10.5 Configuration SSL/TLS
  - 10.5.1 OpenSSL sur Windows
  - 10.5.2 OpenSSL sur Ubuntu
- 10.6 Clients et serveurs WebSocket
- 10.7 Protocoles binaires personnalisés
- 10.8 RPC et communication inter-processus
  - 10.8.1 Named Pipes (Windows)
  - 10.8.2 Unix Domain Sockets (Linux)
- 10.9 mORMot pour services REST/SOA
- 10.10 gRPC et Protocol Buffers
- 10.11 P2P et protocoles décentralisés
- 10.12 Firewall et configuration réseau par OS

## 11. Multithreading et Concurrence

- 11.1 TThread et synchronisation avancée
- 11.2 Thread pools et workers
- 11.3 Structures de données thread-safe
- 11.4 Lock-free programming
- 11.5 Parallel programming library
- 11.6 Async/Await patterns
- 11.7 Différences de scheduling Windows/Linux
- 11.8 Acteurs et passage de messages
- 11.9 Coroutines et fibers
- 11.10 Optimisation multicœur
- 11.11 Affinité processeur par OS
- 11.12 Débogage d'applications concurrentes

## 12. Interfaces Graphiques Avancées

- 12.1 Custom drawing et Canvas avancé
- 12.2 BGRABitmap pour graphiques avancés
- 12.3 OpenGL multi-plateforme
  - 12.3.1 Configuration OpenGL Windows
  - 12.3.2 Configuration OpenGL Linux/Mesa
- 12.4 Vulkan et rendu moderne
- 12.5 Animations et transitions
- 12.6 Docking et interfaces modulaires
- 12.7 Éditeurs et designers intégrés
- 12.8 Graphiques vectoriels SVG
- 12.9 Traitement d'images avancé
- 12.10 Vision par ordinateur avec OpenCV
- 12.11 Accélération GPU (CUDA/OpenCL)

## 13. Développement Mobile et Embarqué

- 13.1 LAMW - Lazarus Android Module Wizard
- 13.2 Architecture Android et JNI
- 13.3 Interfaces natives Android
- 13.4 Custom Drawn pour interfaces mobiles
- 13.5 Capteurs et périphériques mobiles
- 13.6 iOS avec FreePascal (expérimental)
- 13.7 Raspberry Pi
  - 13.7.1 Cross-compilation depuis Windows
  - 13.7.2 Développement natif sur Ubuntu ARM
- 13.8 Arduino et microcontrôleurs
- 13.9 Optimisation pour appareils mobiles
- 13.10 Distribution sur stores

## 14. Systèmes Embarqués et IoT

- 14.1 FreePascal pour microcontrôleurs
- 14.2 AVR et Arduino avec FreePascal
- 14.3 ARM Cortex-M et STM32
- 14.4 Raspberry Pi et Linux embarqué
- 14.5 Protocoles IoT (MQTT, CoAP, LoRaWAN)
- 14.6 Communication série
  - 14.6.1 Ports COM Windows
  - 14.6.2 /dev/tty* Linux
- 14.7 GPIO et interfaces matérielles
- 14.8 Temps réel et RTOS
- 14.9 Drivers et accès matériel direct
- 14.10 Optimisation mémoire pour embarqué
- 14.11 Edge computing

## 15. Intelligence Artificielle et Machine Learning

- 15.1 Bindings TensorFlow pour FreePascal
- 15.2 Réseaux de neurones from scratch
- 15.3 Computer Vision avec OpenCV
- 15.4 NLP et traitement de texte
- 15.5 Algorithmes génétiques
- 15.6 Apprentissage par renforcement
- 15.7 Intégration avec Python
  - 15.7.1 Python4Lazarus sur Windows
  - 15.7.2 Python4Lazarus sur Ubuntu
- 15.8 ONNX et modèles portables
- 15.9 GPU computing avec CUDA/OpenCL
- 15.10 Déploiement de modèles IA

## 16. Traitement de Données et Calcul Scientifique

- 16.1 NumLib - Calcul numérique
- 16.2 TAChart pour visualisations
- 16.3 Traitement du signal (DSP)
- 16.4 Algèbre linéaire et matrices
- 16.5 Statistiques avancées
- 16.6 FFT et analyse spectrale
- 16.7 Optimisation et solveurs
- 16.8 Calcul parallèle et vectorisation
- 16.9 Intégration avec R et Python
- 16.10 Bibliothèques scientifiques par OS

## 17. Sécurité et Cryptographie

- 17.1 DCPCrypt et algorithmes cryptographiques
- 17.2 TLS/SSL avec OpenSSL
  - 17.2.1 Configuration OpenSSL Windows
  - 17.2.2 Configuration OpenSSL Ubuntu
- 17.3 Authentification et OAuth 2.0
- 17.4 JWT et tokens sécurisés
- 17.5 Hashing et signatures numériques
- 17.6 Stockage sécurisé de données
  - 17.6.1 DPAPI Windows
  - 17.6.2 Keyring Linux/GNOME
- 17.7 Analyse de vulnérabilités
- 17.8 Obfuscation et protection du code
- 17.9 Sandboxing et isolation
- 17.10 Audit et conformité GDPR
- 17.11 SELinux/AppArmor vs Windows Defender

## 18. Tests et Qualité du Code

- 18.1 FPCUnit - Framework de tests unitaires
- 18.2 Tests d'intégration automatisés
- 18.3 Mocking et injection de dépendances
- 18.4 Couverture de code
  - 18.4.1 Profiling Windows (DProf)
  - 18.4.2 Profiling Linux (gprof, Valgrind)
- 18.5 Analyse statique du code
- 18.6 Tests de performance et benchmarking
- 18.7 Tests de charge et stress
- 18.8 Fuzzing et tests aléatoires
- 18.9 CI/CD multi-plateforme
  - 18.9.1 GitHub Actions Windows/Ubuntu
  - 18.9.2 GitLab CI avec runners multi-OS
- 18.10 Documentation automatique

## 19. Interopérabilité et Bindings

- 19.1 Création de bibliothèques partagées
  - 19.1.1 DLL Windows et exports
  - 19.1.2 Shared Objects (.so) Linux
- 19.2 Bindings C/C++ avancés
- 19.3 Interfaçage avec Python
- 19.4 COM/ActiveX sous Windows
- 19.5 D-Bus sous Linux
- 19.6 Java Native Interface (JNI)
- 19.7 .NET interop (Windows)
- 19.8 Mono interop (Linux)
- 19.9 WebAssembly et JavaScript
- 19.10 Génération automatique de bindings
- 19.11 FFI (Foreign Function Interface)

## 20. Optimisation et Performance

- 20.1 Profiling multi-plateforme
  - 20.1.1 Intel VTune (Windows)
  - 20.1.2 Perf et Valgrind (Linux)
- 20.2 Optimisation mémoire et caches
- 20.3 SIMD et vectorisation
- 20.4 Optimisations spécifiques CPU
- 20.5 Structures de données optimales
- 20.6 Algorithmes haute performance
- 20.7 Memory pools et allocateurs custom
- 20.8 Lazy evaluation et memoization
- 20.9 Benchmarking systématique
- 20.10 Optimisation pour différentes architectures
- 20.11 Comparaison de performance Windows/Linux

## 21. Architecture Logicielle Avancée

- 21.1 Domain-Driven Design avec FreePascal
- 21.2 Microservices et architectures distribuées
- 21.3 Event Sourcing et CQRS
- 21.4 Hexagonal Architecture
- 21.5 Dependency Injection containers
- 21.6 Plugin architectures portables
- 21.7 Message queues et event bus
- 21.8 Saga pattern et transactions distribuées
- 21.9 API Gateway patterns
- 21.10 Service mesh et observabilité
- 21.11 Architecture cloud-native

## 22. DevOps et Déploiement Multi-OS

- 22.1 Conteneurisation avec Docker
  - 22.1.1 Docker Desktop Windows
  - 22.1.2 Docker natif Ubuntu
- 22.2 Orchestration Kubernetes
- 22.3 Infrastructure as Code (Terraform, Ansible)
- 22.4 Pipelines CI/CD complets
- 22.5 Build multi-plateforme automatisé
- 22.6 Packaging et distribution
  - 22.6.1 Installateurs Windows (Inno Setup, NSIS, MSI)
  - 22.6.2 Paquets Linux (DEB, RPM, AppImage, Snap)
- 22.7 Monitoring et métriques (Prometheus)
- 22.8 Logging centralisé (ELK stack)
- 22.9 Blue-Green deployments
- 22.10 Feature flags et A/B testing
- 22.11 Gestion de configuration
- 22.12 Disaster recovery

## 23. Développement de Jeux

- 23.1 Castle Game Engine
- 23.2 ZenGL et frameworks 2D
- 23.3 Physics engines (Box2D, Bullet)
- 23.4 Audio multi-plateforme
  - 23.4.1 DirectSound/XAudio2 (Windows)
  - 23.4.2 ALSA/PulseAudio (Linux)
  - 23.4.3 OpenAL (universel)
- 23.5 Input devices et contrôleurs
- 23.6 Réseaux pour jeux multijoueurs
- 23.7 Scripting et modding
- 23.8 Optimisation pour jeux
- 23.9 Distribution Steam (Windows/Linux)
- 23.10 Réalité virtuelle et augmentée

## 24. Compilateur et Outils Avancés

- 24.1 Architecture interne du FPC
- 24.2 Développement de backends
- 24.3 Optimisations du compilateur
- 24.4 Génération de code custom
- 24.5 Preprocesseur et macros
- 24.6 Analyseurs syntaxiques (fcl-passrc)
- 24.7 Outils de build personnalisés
- 24.8 Cross-compilation avancée
  - 24.8.1 Windows → Linux
  - 24.8.2 Linux → Windows
  - 24.8.3 Toolchains croisés
- 24.9 Intégration WSL/WSL2
- 24.10 Remote debugging cross-platform

## 25. Projets Complexes et Études de Cas

- 25.1 ERP complet multi-plateforme
- 25.2 Plateforme SaaS multi-tenant
- 25.3 Système de trading haute fréquence
- 25.4 IDE ou éditeur de code avancé portable
- 25.5 Moteur de workflow/BPM
- 25.6 Système de monitoring distribué
- 25.7 Blockchain et smart contracts
- 25.8 Compilateur ou interpréteur
- 25.9 Suite bureautique portable
- 25.10 Système de gestion hospitalière

## 26. Communauté et Écosystème

- 26.1 Contribution au projet FreePascal/Lazarus
- 26.2 Création et maintenance de packages
- 26.3 Forums et ressources communautaires
- 26.4 Documentation et tutoriels
- 26.5 Conférences et meetups
- 26.6 Projets open source notables
- 26.7 Migration depuis Delphi
  - 26.7.1 Portage de projets Windows
  - 26.7.2 Adaptation pour Linux
- 26.8 Opportunités professionnelles
- 26.9 Certification et évaluation
- 26.10 Roadmap et futur du projet
- 26.11 Ressources spécifiques Windows/Ubuntu
