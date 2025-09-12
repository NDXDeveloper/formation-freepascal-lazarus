🔝 Retour au [Sommaire](/SOMMAIRE.md)

# 2.3 Création et gestion de packages dans Lazarus

## Introduction : Qu'est-ce qu'un package Lazarus ?

Un **package** (ou paquet) dans Lazarus est comme une boîte à outils réutilisable. Imaginez que vous ayez créé un composant génial (par exemple, un bouton animé) et que vous vouliez l'utiliser dans plusieurs projets, ou le partager avec d'autres développeurs. Au lieu de copier-coller le code partout, vous créez un package qui contient ce composant.

Les packages peuvent contenir :
- 📦 **Des composants visuels** (boutons, grilles, graphiques personnalisés)
- 🔧 **Des unités de code** (fonctions utilitaires, classes métier)
- 🎨 **Des ressources** (icônes, images, fichiers de configuration)
- 🔌 **Des extensions d'IDE** (nouveaux menus, outils, fenêtres)

## Types de packages

### Packages de conception (Design-time)

Ces packages s'installent dans l'IDE et ajoutent de nouvelles fonctionnalités :

```
Exemples :
├── Nouveaux composants dans la palette
├── Éditeurs de propriétés personnalisés
├── Experts et assistants
└── Extensions de menu
```

**💡 Reconnaissable par** : Le suffixe "Dsgn" dans le nom (ex: `AnchorDockingDsgn.lpk`)

### Packages d'exécution (Runtime)

Ces packages contiennent le code qui sera utilisé dans vos applications :

```
Exemples :
├── Bibliothèques de fonctions
├── Classes métier
├── Moteurs de calcul
└── Gestionnaires de données
```

### Packages mixtes (Design + Runtime)

La plupart des packages combinent les deux :
- La partie **design** pour l'intégration dans l'IDE
- La partie **runtime** pour le code de l'application

## Structure d'un package

Un package Lazarus suit cette organisation :

```
MonPackage/
├── monpackage.lpk          # Fichier principal du package
├── src/                     # Sources
│   ├── moncomposant.pas    # Composant principal
│   ├── utils.pas           # Unités utilitaires
│   └── register.pas        # Enregistrement dans l'IDE
├── lib/                     # Fichiers compilés (créé automatiquement)
│   └── x86_64-win64/       # Selon votre plateforme
├── images/                  # Ressources
│   └── icons.res           # Icônes pour la palette
└── docs/                    # Documentation
    └── readme.md
```

## Créer votre premier package

### Étape 1 : Nouveau package

Menu **Paquet** → **Nouveau paquet...**

Une fenêtre s'ouvre avec les options de base :

```
Nouveau Package
├── Nom : MonPremierPackage
├── Type : [Composant]
├── Version : 1.0.0.0
└── Description : Mon premier package Lazarus
```

**📝 Conventions de nommage** :
- Utilisez des noms descriptifs (ex: `DatabaseTools`, `GraphicsExtended`)
- Évitez les espaces et caractères spéciaux
- Ajoutez un préfixe pour votre organisation (ex: `ACME_DatabaseTools`)

### Étape 2 : L'éditeur de package

Après création, l'éditeur de package s'ouvre :

```
┌─ MonPremierPackage.lpk ─────────────────────┐
│ Toolbar: [Compiler] [Ajouter] [Options]     │
├─────────────────────────────────────────────┤
│ Fichiers:                                   │
│ └── (vide pour l'instant)                   │
│                                             │
│ Packages requis:                            │
│ └── FCL                                     │
│ └── LCL (si composants visuels)             │
└─────────────────────────────────────────────┘
```

### Étape 3 : Ajouter des fichiers

Cliquez sur **Ajouter** → **Nouveau fichier** :

```
Types de fichiers à ajouter :
├── Unité simple (.pas)
├── Composant visuel (TComponent descendant)
├── Formulaire (.lfm + .pas)
└── Fichier existant
```

### Étape 4 : Créer un composant simple

Voici un exemple de composant basique à ajouter :

```pascal
unit MonBoutonSpecial;

{$mode objfpc}{$H+}

interface

uses
  Classes, SysUtils, Controls, StdCtrls, Graphics;

type
  { TMonBoutonSpecial }
  TMonBoutonSpecial = class(TButton)
  private
    FColorHover: TColor;
    FIsHovering: Boolean;
  protected
    procedure MouseEnter; override;
    procedure MouseLeave; override;
    procedure Paint; override;
  published
    property ColorHover: TColor read FColorHover write FColorHover default clSkyBlue;
  public
    constructor Create(AOwner: TComponent); override;
  end;

implementation

constructor TMonBoutonSpecial.Create(AOwner: TComponent);
begin
  inherited Create(AOwner);
  FColorHover := clSkyBlue;
  FIsHovering := False;
end;

procedure TMonBoutonSpecial.MouseEnter;
begin
  inherited;
  FIsHovering := True;
  Invalidate; // Redessiner
end;

procedure TMonBoutonSpecial.MouseLeave;
begin
  inherited;
  FIsHovering := False;
  Invalidate;
end;

procedure TMonBoutonSpecial.Paint;
var
  OldColor: TColor;
begin
  if FIsHovering then
  begin
    OldColor := Color;
    Color := FColorHover;
    inherited Paint;
    Color := OldColor;
  end
  else
    inherited Paint;
end;

end.
```

### Étape 5 : Enregistrer le composant

Créez un fichier `register.pas` pour enregistrer votre composant dans l'IDE :

```pascal
unit Register;

{$mode objfpc}{$H+}

interface

uses
  Classes, SysUtils, LResources, MonBoutonSpecial;

procedure Register;

implementation

procedure Register;
begin
  // Enregistrer dans l'onglet 'Mes Composants' de la palette
  RegisterComponents('Mes Composants', [TMonBoutonSpecial]);
end;

initialization
  // Si vous avez des icônes pour la palette
  {$I monpackage_icons.lrs}

end.
```

## Configuration du package

### Options du package

Clic droit sur le package → **Options** ou bouton **Options** :

#### Onglet "Package"

```
Informations du package :
├── Nom : MonPremierPackage
├── Version :
│   ├── Majeure : 1
│   ├── Mineure : 0
│   ├── Release : 0
│   └── Build : 0 (auto-incrémenté)
├── Auteur : Votre Nom
├── Licence : [LGPL / GPL / MIT / etc.]
└── Description : Description détaillée
```

**🔢 Versioning** : Suivez le schéma sémantique :
- **Majeure** : Changements incompatibles
- **Mineure** : Nouvelles fonctionnalités compatibles
- **Release** : Corrections de bugs
- **Build** : Compilation (auto)

#### Onglet "Compilation"

```
Options de compilation :
├── Type :
│   ☑ Designtime et Runtime
│   ☐ Seulement Runtime
│   ☐ Seulement Designtime
├── Optimisation : [Niveau 1]
├── Débogage :
│   ☑ Générer infos de débogage
│   ☐ Utiliser Heaptrc (détection fuites mémoire)
└── Chemin de sortie : lib/$(TargetCPU)-$(TargetOS)
```

#### Onglet "IDE Integration"

```
Intégration IDE :
├── Type de package : [Composant]
├── Icône : [Parcourir...]
├── Catégorie : Composants visuels
└── Mots-clés : bouton, hover, animation
```

### Dépendances du package

Les packages peuvent dépendre d'autres packages :

```
Packages requis (Dependencies) :
├── FCL (Free Component Library) - Toujours requis
├── LCL (Lazarus Component Library) - Pour composants visuels
├── LCLBase - Version allégée de LCL
└── Vos autres packages custom
```

**Pour ajouter une dépendance** :
1. Bouton **Ajouter** → **Nouveau requirement**
2. Sélectionnez le package dans la liste
3. Spécifiez la version minimale si nécessaire

## Compiler et installer un package

### Compilation simple

Bouton **Compiler** dans l'éditeur de package ou **Ctrl+F9**

Messages de compilation :
```
Compiling package MonPremierPackage 1.0.0.0
├── Parsing MonBoutonSpecial.pas
├── Parsing Register.pas
├── Linking MonPremierPackage.ppu
└── Success: Package compiled successfully
```

### Installation dans l'IDE

Pour les packages avec composants design-time :

1. Bouton **Utiliser** → **Installer**
2. Lazarus vous informe qu'il doit se recompiler
3. Cliquez **Oui** pour reconstruire l'IDE
4. L'IDE redémarre avec votre package installé

**⚠️ Important** : Sauvegardez votre travail avant ! La recompilation de l'IDE peut échouer.

### Utilisation dans un projet

Pour les packages runtime uniquement :

1. Dans votre projet : **Projet** → **Inspecteur de projet**
2. **Ajouter** → **Nouveau requirement**
3. Sélectionnez votre package
4. Il sera automatiquement compilé avec votre projet

## Gestion des packages installés

### Voir les packages installés

Menu **Paquet** → **Installer/Désinstaller des packages**

```
┌─ Packages Installés/Disponibles ────────────┐
│ Installés:              │ Disponibles:      │
│ ├── AnchorDocking      │ ├── CGILazarus    │
│ ├── MonPremierPackage  │ ├── DataDict      │
│ ├── SynEdit            │ ├── EducationLaz  │
│ └── TurboPowerIPro     │ └── PascalScript  │
│                         │                   │
│ [Désinstaller >>]       │ [<< Installer]    │
└──────────────────────────────────────────────┘
```

### Désinstaller un package

1. Sélectionnez le package dans "Installés"
2. Cliquez **Désinstaller >>**
3. **Sauvegarder et reconstruire l'IDE**
4. L'IDE redémarre sans le package

### Mettre à jour un package

1. Ouvrez le package : **Paquet** → **Ouvrir un paquet** (.lpk)
2. Modifiez le code/composants
3. Incrémentez la version
4. **Compiler** puis **Installer**

## Online Package Manager (OPM)

Lazarus inclut un gestionnaire de packages en ligne :

### Accéder à OPM

Menu **Paquet** → **Online Package Manager**

```
┌─ Online Package Manager ─────────────────────┐
│ Catégories:          │ Packages disponibles: │
│ ├── Graphics         │ ├── BGRABitmap 11.5   │
│ ├── Database         │ ├── Castle Game Engine│
│ ├── Network          │ ├── Indy 10.6         │
│ └── System           │ └── ZEOS 8.0          │
│                      │                       │
│ [Filtrer: _______]   │ [Installer] [Infos]   │
└──────────────────────────────────────────────┘
```

### Installer depuis OPM

1. Sélectionnez le package
2. Cliquez **Installer**
3. OPM télécharge et compile automatiquement
4. Redémarrage de l'IDE si nécessaire

**🌐 Avantages d'OPM** :
- Accès à des centaines de packages
- Gestion automatique des dépendances
- Mises à jour facilitées
- Évaluations et commentaires communautaires

## Créer des icônes pour la palette

### Format des icônes

Les composants dans la palette ont besoin d'icônes :
- **Format** : PNG ou BMP
- **Taille** : 24x24 pixels (standard) ou 16x16
- **Transparence** : Supportée avec PNG

### Créer le fichier de ressources

1. Préparez vos images : `monbouton.png`
2. Créez un fichier `monpackage_icons.lrs` :

```pascal
// Utiliser lazres.exe (dans le dossier tools de Lazarus)
lazres monpackage_icons.lrs monbouton.png
```

Ou directement dans le code :
```pascal
procedure Register;
begin
  RegisterComponents('Mes Composants', [TMonBoutonSpecial]);
  // L'icône doit avoir le même nom que la classe
end;

initialization
  {$I monpackage_icons.lrs}
```

## Packages multi-plateformes

### Compilation conditionnelle

Pour un package compatible Windows/Linux :

```pascal
unit CrossPlatformUtils;

{$mode objfpc}{$H+}

interface

uses
  Classes, SysUtils
  {$IFDEF WINDOWS}
  , Windows, Registry
  {$ENDIF}
  {$IFDEF UNIX}
  , BaseUnix, Unix
  {$ENDIF};

type
  TCrossPlatformHelper = class
  public
    function GetSystemPath: string;
    function GetConfigPath: string;
  end;

implementation

function TCrossPlatformHelper.GetSystemPath: string;
begin
  {$IFDEF WINDOWS}
  Result := GetEnvironmentVariable('WINDIR');
  {$ENDIF}
  {$IFDEF UNIX}
  Result := '/usr/bin';
  {$ENDIF}
end;

function TCrossPlatformHelper.GetConfigPath: string;
begin
  {$IFDEF WINDOWS}
  Result := GetEnvironmentVariable('APPDATA');
  {$ENDIF}
  {$IFDEF UNIX}
  Result := GetEnvironmentVariable('HOME') + '/.config';
  {$ENDIF}
end;

end.
```

### Options spécifiques par OS

Dans les options du package, onglet **Autre** :

```
Conditions personnalisées :
├── Si OS = Windows :
│   └── Ajouter unité : WindowsSpecific.pas
├── Si OS = Linux :
│   └── Ajouter unité : LinuxSpecific.pas
└── Si CPU = ARM :
    └── Options : -O2 -CfVFPV3
```

## Distribuer vos packages

### Package source

Structure recommandée pour la distribution :

```
MonPackage_v1.0/
├── source/           # Code source
├── examples/         # Exemples d'utilisation
├── docs/            # Documentation
├── LICENSE.txt      # Licence
├── README.md        # Instructions
└── INSTALL.txt      # Guide d'installation
```

### Créer une archive

```bash
# Linux
tar -czf MonPackage_v1.0.tar.gz MonPackage_v1.0/

# Windows (avec 7-Zip)
7z a MonPackage_v1.0.zip MonPackage_v1.0/
```

### Documentation du package

Créez un `README.md` clair :

```markdown
# MonPremierPackage

## Description
Package Lazarus ajoutant un bouton avec effet hover.

## Installation
1. Ouvrir MonPremierPackage.lpk dans Lazarus
2. Compiler
3. Installer (pour composants design-time)

## Utilisation
```pascal
uses MonBoutonSpecial;

var
  Btn: TMonBoutonSpecial;
begin
  Btn := TMonBoutonSpecial.Create(Self);
  Btn.Parent := Self;
  Btn.ColorHover := clAqua;
end;
```

## Compatibilité
- Lazarus 2.0+
- FPC 3.2+
- Windows, Linux, macOS

## Licence
LGPL v3
```

## Packages statiques vs dynamiques

### Packages statiques (par défaut)

Le code est compilé directement dans votre exécutable :

**Avantages** :
- ✅ Un seul fichier .exe à distribuer
- ✅ Pas de problèmes de versions
- ✅ Performance optimale

**Inconvénients** :
- ❌ Exécutable plus gros
- ❌ Duplication si plusieurs apps utilisent le même package

### Packages dynamiques (DLL/SO)

Le code est dans une bibliothèque séparée :

**Configuration** :
```
Options du package → Compilation :
☑ Créer une bibliothèque dynamique
└── Nom : MonPackage.dll (Windows) / libMonPackage.so (Linux)
```

**Avantages** :
- ✅ Exécutable plus petit
- ✅ Partage entre applications
- ✅ Mise à jour sans recompiler l'app

**Inconvénients** :
- ❌ Distribution plus complexe
- ❌ "DLL Hell" potentiel

## Bonnes pratiques

### Organisation du code

```
Structure recommandée :
├── Core/           # Logique métier
├── Components/     # Composants visuels
├── Designers/      # Éditeurs de propriétés
├── Utils/         # Fonctions utilitaires
└── Resources/     # Images, configs
```

### Nommage et préfixes

```pascal
// Utilisez un préfixe unique pour éviter les conflits
type
  TMPButton = class(TButton)      // MP = MonPackage
  TMPEdit = class(TEdit)
  TMPUtils = class
```

### Documentation inline

```pascal
type
  { TMonBoutonSpecial }
  { Bouton avec effet de survol personnalisable.
    Exemple d'utilisation :
    - Créer le bouton
    - Définir ColorHover
    - L'effet est automatique }
  TMonBoutonSpecial = class(TButton)
  private
    FColorHover: TColor;
  published
    { Couleur affichée au survol de la souris }
    property ColorHover: TColor read FColorHover write FColorHover;
  end;
```

### Tests unitaires

Créez un projet de test pour votre package :

```pascal
program TestMonPackage;

uses
  TestFramework, MonBoutonSpecial;

type
  TTestMonBouton = class(TTestCase)
  published
    procedure TestCreate;
    procedure TestColorHover;
  end;

procedure TTestMonBouton.TestCreate;
var
  Btn: TMonBoutonSpecial;
begin
  Btn := TMonBoutonSpecial.Create(nil);
  try
    CheckNotNull(Btn, 'Button creation failed');
  finally
    Btn.Free;
  end;
end;
```

## Dépannage courant

### Le package ne compile pas

**Vérifiez** :
1. Les chemins des unités sont corrects
2. Les dépendances sont installées
3. La version de FPC/Lazarus est compatible
4. Les directives de compilation sont correctes

### L'IDE ne redémarre pas après installation

**Solution** :
1. Lancez Lazarus en mode sans échec : `lazarus --skip-last-project`
2. Désinstallez le package problématique
3. Vérifiez le code du package
4. Réessayez l'installation

### Les icônes n'apparaissent pas

**Vérifiez** :
1. Le fichier .lrs est bien inclus
2. Les noms d'icônes correspondent aux noms de classes
3. Le format d'image est supporté
4. La taille est correcte (24x24)

### Conflits de noms

**Message** : "Identifier already defined"

**Solution** :
1. Utilisez des préfixes uniques
2. Vérifiez les uses clauses
3. Utilisez des namespaces si nécessaire

## Packages avancés

### Éditeurs de propriétés personnalisés

```pascal
type
  TColorPropertyEditor = class(TPropertyEditor)
  public
    procedure Edit; override;
    function GetAttributes: TPropertyAttributes; override;
  end;

procedure TColorPropertyEditor.Edit;
var
  ColorDialog: TColorDialog;
begin
  ColorDialog := TColorDialog.Create(nil);
  try
    ColorDialog.Color := GetOrdValue;
    if ColorDialog.Execute then
      SetOrdValue(ColorDialog.Color);
  finally
    ColorDialog.Free;
  end;
end;

// Enregistrement
RegisterPropertyEditor(TypeInfo(TColor), TMonBoutonSpecial,
                      'ColorHover', TColorPropertyEditor);
```

### Experts et assistants

```pascal
type
  TMonExpert = class(TIDEMenuCommand)
  public
    procedure Execute; override;
  end;

procedure TMonExpert.Execute;
begin
  ShowMessage('Mon expert fonctionne !');
  // Générer du code, créer des fichiers, etc.
end;

// Enregistrement dans le menu IDE
RegisterIDEMenuCommand(itmSecondaryTools, 'MonExpert',
                      'Mon Expert Tool', nil, @TMonExpert.Execute);
```

## Conclusion

Les packages sont l'épine dorsale de l'écosystème Lazarus. Ils permettent de créer du code réutilisable, de partager vos créations avec la communauté, et d'étendre l'IDE selon vos besoins.

**Points clés à retenir** :
- Un package = une unité de code réutilisable
- Design-time pour l'IDE, Runtime pour l'application
- L'OPM donne accès à des centaines de packages
- Documentez et testez vos packages
- Pensez multi-plateforme dès le début

La maîtrise des packages vous permet de :
- 🚀 Accélérer le développement en réutilisant du code
- 🎁 Partager vos créations avec la communauté
- 🔧 Personnaliser Lazarus selon vos besoins
- 📚 Organiser votre code de manière professionnelle

Dans la prochaine section (2.4), nous verrons comment utiliser les outils de refactoring pour améliorer et restructurer votre code efficacement.

⏭️ [Outils de refactoring intégrés](/02-maitrise-ide-lazarus/04-outils-refactoring-integres.md)
