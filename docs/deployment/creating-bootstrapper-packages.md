---
title: Vytváření balíčků bootstrapperu
ms.date: 05/02/2018
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], prerequisites
- deploying applications [Visual Studio], custom prerequisites
- prerequisites, custom
- RedistList file
- custom prerequisites
- redistributables list
ms.assetid: ba1a785b-693d-446b-bcae-b88cadee73d1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3dc22b775af048cc3138d6930a835a00c9d97b2a
ms.sourcegitcommit: 9cfd3ef6c65f671a26322320818212a1ed5955fe
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/26/2019
ms.locfileid: "68533326"
---
# <a name="create-bootstrapper-packages"></a>Vytváření balíčků bootstrapperu
Instalační program je obecný instalační program, který se dá nakonfigurovat tak, aby zjišťoval a instaloval distribuovatelné součásti, jako jsou soubory Instalační služba systému Windows ( *. msi*) a spustitelné programy. Instalační program je také označován jako zaváděcí nástroj. Je naprogramován sadou manifestů XML, které určují metadata pro správu instalace součásti.  Každá Redistribuovatelná součást, která se zobrazí v dialogovém okně **předpoklady** pro ClickOnce, je balíček zaváděcího nástroje. Balíček zaváděcího nástroje je skupina adresářů a souborů, které obsahují soubory manifestu, které popisují, jak by měla být požadovaná součást nainstalována.

Zaváděcí nástroj nejprve zjistí, zda některé z požadovaných součástí jsou již nainstalovány. Pokud požadavky nejsou nainstalovány, nejprve si zaváděcí nástroj zobrazí licenční smlouvy. Za druhé se po přijetí licenčních smluv koncovým uživatelem spustí instalace požadovaných součástí. V opačném případě, pokud jsou zjištěny všechny požadavky, zaváděcí nástroj pouze spustí instalační program aplikace.

## <a name="create-custom-bootstrapper-packages"></a>Vytvoření vlastních balíčků zaváděcího nástroje
Manifesty zaváděcího nástroje můžete vygenerovat pomocí editoru XML v aplikaci Visual Studio. Příklad vytvoření balíčku zaváděcího nástroje najdete v tématu [Názorný postup: Vytvořte vlastního zaváděcího nástroje s výzvou](../deployment/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt.md)k ochraně osobních údajů.

Chcete-li vytvořit balíček zaváděcího nástroje, je nutné vytvořit manifest produktu a pro každou lokalizovanou verzi komponenty také manifest balíčku.

* Manifest produktu *Product. XML*obsahuje všechna jazyková a neutrální metadata pro balíček. Obsahuje metadata společná pro všechny lokalizované verze distribuovatelné součásti.  Chcete-li vytvořit tento soubor [, přečtěte si téma How to: Vytvořte manifest](../deployment/how-to-create-a-product-manifest.md)produktu.

* Manifest balíčku, *Package. XML*, obsahuje metadata specifická pro jazyk; obvykle obsahuje lokalizované chybové zprávy. Komponenta musí mít alespoň jeden manifest balíčku pro každou lokalizovanou verzi této součásti. Chcete-li vytvořit tento soubor [, přečtěte si téma How to: Vytvořte manifest](../deployment/how-to-create-a-package-manifest.md)balíčku.

Po vytvoření těchto souborů vložte soubor manifestu produktu do složky s názvem pro vlastní zaváděcí nástroj. Soubor manifestu balíčku přejde do složky s názvem pro národní prostředí. Například pokud je soubor manifestu balíčku pro anglickou distribuci, uložte soubor do složky s názvem en. Tento postup opakujte pro každé národní prostředí, například ja pro japonštinu a de pro němčinu. Konečný balíček vlastního zaváděcího nástroje může mít následující strukturu složek.

```
CustomBootstrapperPackage
  product.xml
  CustomBootstrapper.msi
  de
    eula.rtf
    package.xml
  en
    eula.rtf
    package.xml
  ja
    eula.rtf
    package.xml
```

Potom zkopírujte redistribuovatelné soubory do umístění složky zaváděcího nástroje. Další informace najdete v tématu [jak: Vytvořte lokalizovaný balíček](../deployment/how-to-create-a-localized-bootstrapper-package.md)zaváděcího nástroje.

```
*\Program Files (x86)\Microsoft SDKs\ClickOnce Bootstrapper*
```

nebo, pro starší verze sady Visual Studio

```
*\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
```

or

```
*\Program Files (x86)\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
```

Umístění složky zaváděcího nástroje můžete také najít z hodnoty **cesty** v následujícím klíči registru:

```
*HKLM\Software\Microsoft\GenericBootstrapper*
```

V 64 systémech použijte následující klíč registru:

```
*HKLM\Software\Wow6432Node\Microsoft\GenericBootstrapper*
```

Každá Distribuovatelný součást se zobrazí ve své vlastní podsložce v adresáři Packages. Manifest produktu a redistribuovatelné soubory musí být vloženy do této podsložky. Lokalizované verze komponent a manifestů balíčku musí být umístěny v podsložkách s názvem podle názvu jazykové verze.

Po zkopírování těchto souborů do složky zaváděcího nástroje se balíček zaváděcího nástroje automaticky zobrazí v dialogovém okně **předpoklady** sady Visual Studio. Pokud se vlastní balíček zaváděcího nástroje nezobrazí, zavřete a znovu otevřete dialogové okno **požadavky** . Další informace najdete v [dialogovém okně předpoklady](../ide/reference/prerequisites-dialog-box.md).

V následující tabulce jsou uvedeny vlastnosti, které zaváděcí nástroj automaticky vyplní.

|Vlastnost|Popis|
|--------------|-----------------|
|ApplicationName|Název aplikace|
|ProcessorArchitecture|Procesor a bity na slova platformy, na kterou cílí spustitelný soubor. Mezi hodnoty patří následující:<br /><br /> – Intel<br />– IA64<br />– AMD64|
|[Version9x](/windows/desktop/Msi/version9x)|Číslo verze pro operační systémy Microsoft Windows 95, Windows 98 nebo Windows MILLENNIUM. Syntaxe verze je hlavní_verze. podverze. ServicePack.|
|[VersionNT](/windows/desktop/Msi/versionnt)|Číslo verze pro operační systémy Windows NT, Windows 2000, Windows XP, Windows Vista, Windows Server 2008 nebo Windows 7. Syntaxe verze je hlavní_verze. podverze. ServicePack.|
|[VersionMSI](/windows/desktop/Msi/versionmsi)|Verze sestavení Instalační služba systému Windows (MSI. dll), která se má spustit během instalace|
|[AdminUser](/windows/desktop/Msi/adminuser)|Tato vlastnost je nastavena, pokud má uživatel oprávnění správce. Hodnoty jsou true nebo false.|
|InstallMode|Režim instalace označuje, odkud je nutné součást nainstalovat. Mezi hodnoty patří následující:<br /><br /> -HomeSite – požadavky jsou nainstalovány z webu dodavatele.<br />-SpecificSite – požadavky jsou nainstalovány z umístění, které jste vybrali.<br />-SameSite – požadavky jsou nainstalovány ze stejného umístění jako aplikace.|

## <a name="separate-redistributables-from-application-installations"></a>Samostatné Distribuovatelné součásti z instalace aplikace
Můžete zabránit nasazení vašich redistribuovatelných souborů v projektech instalace. K tomu je potřeba vytvořit Distribuovatelný seznam ve složce RedistList v adresáři .NET Framework:

`%ProgramFiles%\Microsoft.NET\RedistList`

Distribuovatelný seznam je soubor XML, který byste měli pojmenovat v následujícím formátu: *Název společnosti >.\< \< Název součásti >. RedistList. XML*. Takže pokud se například komponenta nazývá DataWidgets vytvořená Acme, použijte *Acme. DataWidgets. RedistList. XML*. Příklad redistribuovatelného seznamu obsahu může vypadat takto:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<FileList Redist="Acme.DataWidgets" >
<File AssemblyName="Acme.DataGrid" Version="1.0.0.0" PublicKeyToken="b03f5f7f11d50a3a" Culture="neutral" ProcessorArchitecture="MSIL" InGAC="true" />
</FileList>
```

## <a name="see-also"></a>Viz také:
- [Postupy: Instalace požadavků s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
- [Dialogové okno požadavky](../ide/reference/prerequisites-dialog-box.md)
- [Odkaz na schéma produktu a balíčku](../deployment/product-and-package-schema-reference.md)
- [Použití zaváděcího nástroje sady Visual Studio 2005 k zahájení instalace](http://go.microsoft.com/fwlink/?LinkId=107537)
