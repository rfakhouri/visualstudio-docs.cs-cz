---
title: Vytváření balíčku Instalační služby systému Windows | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- .msi files, VSPackages
- msi files, VSPackages
ms.assetid: 0ce7c21d-0d3f-47fe-a0bb-eed506e32609
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5e92e965f0efe531f1618be509d0a7c9655c573d
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65682543"
---
# <a name="authoring-a-windows-installer-package"></a>Vytvoření balíčku Instalační služby systému Windows
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Datové jednotky modelu Instalační služby systému Windows. Místo psaní skriptu procedury kopírování souborů a zápis položky registru, například vytváříte řádků a sloupců do tabulek databáze, které obsahují data souborů a registru.  
  
## <a name="database-entries"></a>Položky databáze  
 K instalaci VSPackage balíček Instalační služby systému Windows musí obsahovat položky databáze k provádění následujících úloh:  
  
- Hledat systému k vyhledání verze [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] podporuje vašeho balíčku VSPackage (pomocí tabulek Instalační služby systému Windows, které zahrnují AppSearch CompLocator, RegLocator, DrLocator a podpis).  
  
- Zrušit instalaci, pokud žádné podporovanou verzi [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] je nainstalovaná, nebo pokud jiné požadavky na systém ze sady VSPackage není splněná (pomocí tabulky LaunchCondition).  
  
- Instalace balíčku VSPackage a závislé soubory (pomocí adresáře, komponenty a soubor tabulky).  
  
- Přidejte do registru (pomocí tabulky registru) odpovídajícími informacemi pro sady VSPackage.  
  
- Integrace sady VSPackage v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] voláním **/Setup devenv.exe** (pomocí tabulky CustomAction).  
  
  Další informace najdete v tématu [Instalační služby systému Windows](https://msdn.microsoft.com/library/cc185688\(VS.85\).aspx).  
  
## <a name="setup-tools"></a>Instalační program nástroje  
 Různé nástroje třetích stran instalace nabízejí vývojové prostředí pro balíčky Instalační služby systému Windows. Dva bezplatné nástroje vám budou následující:  
  
- InstallShield Limited Edition  
  
   Pomocí sady Visual Studio můžete získat omezenou verzi InstallShield **nový projekt** dialogového okna. Rozbalte **ostatní typy projektů** a pak vyberte **instalace a nasazení**. Vyberte šablonu InstallShield.  
  
- Sada nástrojů XML pro Instalační službu systému Windows  
  
   Sada nástrojů sestavení balíčky Instalační služby systému Windows ze zdrojových souborů XML. Sada nástrojů je projekt open source Microsoftu. Stáhněte si zdrojový kód a spustitelné soubory z [ http://sourceforge.net/projects/wix ](http://sourceforge.net/projects/wix).  
  
  Pro komerční produkty, které se integrují do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] pomocí [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)], naleznete v tématu [ https://marketplace.visualstudio.com/ ](https://marketplace.visualstudio.com/).  
  
## <a name="see-also"></a>Viz také  
 [Instalace balíčků VSPackage pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)
