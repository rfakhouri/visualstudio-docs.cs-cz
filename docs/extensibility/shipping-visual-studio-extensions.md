---
title: Přesouvání rozšíření sady Visual Studio | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSIX deployment
- deployment, VSIX
- satellite DLLs, in VSIX packages
ms.assetid: 13cd263d-25f7-488e-9c1a-cff908caedb6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2ea2217614ed27a98281cce7a3d34b72f74ae803
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62433016"
---
# <a name="shipping-visual-studio-extensions"></a>Odesílání rozšíření sady Visual Studio
Po dokončení vývoje rozšíření, nainstalujte ho na jiné počítače, sdílet s přáteli nebo kolegy nebo ji publikovat na webu Visual Studio Marketplace. V této části vám vysvětlíme, vše, co musíte udělat, aby bylo možné publikovat a spravovat vaše rozšíření: práce se soubory VSIX, publikování, lokalizace a aktualizace.

## <a name="working-with-vsix-extensions"></a>Práce s rozšíření VSIX
 Vytvoření prázdného projektu VSIX a následným přidáním jiná položka šablony do ní můžete vytvořit rozšíření VSIX. Další informace najdete v tématu [šablonou projektu VSIX](../extensibility/vsix-project-template.md).

 Balíček šablony projektů, položku šablony, balíčky VSPackages, součásti Managed Extensibility Framework (MEF), můžete použít formát VSIX **nástrojů** ovládací prvky, sestavení a vlastní typy (to zahrnuje vlastní úvodní stránky pro vizuál Studio 2017). Formát VSIX využívá nasazení založené na souboru. Další informace o balíčcích VSIX, naleznete v tématu [anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md).

 Formát VSIX nepodporuje instalaci fragmentů kódu. Také nepodporuje některých dalších scénářů, jako je například zápis do globální mezipaměti sestavení (GAC) nebo do systémového registru. Pokud budete potřebovat k zápisu do mezipaměti GAC nebo registru v instalaci, musíte použít instalační služby systému Windows. Další informace najdete v tématu [Příprava rozšíření pro Windows Installer nasazení](../extensibility/preparing-extensions-for-windows-installer-deployment.md).

## <a name="publishing-your-extension-to-the-visual-studio-marketplace"></a>Publikování rozšíření sady Visual Studio Marketplace
 Rozšíření ostatním uživatelům můžete distribuovat jednoduše tak, že jejich souboru .vsix poštovní nebo vložení na serveru. Ale nejlepší způsob, jak získat kód dostat do rukou velké množství lidí je umístit jej [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs). Rozšíření sady Visual Studio Marketplace jsou dostupné pro uživatele sady Visual Studio prostřednictvím **rozšíření a aktualizace**. Další informace najdete v tématu [hledání a používání rozšíření sady Visual Studio](../ide/finding-and-using-visual-studio-extensions.md).

 Úplný příklad, který ukazuje, jak nahrát rozšíření pro Visual Studio Marketplace, naleznete v tématu [názorný postup: Publikování rozšíření sady Visual Studio](../extensibility/walkthrough-publishing-a-visual-studio-extension.md).

## <a name="private-galleries"></a>Privátní galerie
 Při vývoji ovládací prvky, šablony a nástroje, můžete je sdílet ve vaší organizaci tím, že publikuje do privátní Galerie na vašem intranetu. Další informace najdete v tématu [privátní Galerie](../extensibility/private-galleries.md).

## <a name="localizing-your-extension"></a>Lokalizace rozšíření
 Pokud máte v plánu uvolnit rozšíření v různých národních prostředí, měli byste zvážit, je lokalizace. Vysvětlení, co je zahrnuta, najdete v článku [lokalizace balíčků VSIX](../extensibility/localizing-vsix-packages.md).

## <a name="updating-and-versioning-your-extension"></a>Aktualizace a správa verzí rozšíření
 Po publikování rozšíření, budou přicházet čas, kdy je potřeba ho aktualizovat. Postup aktualizace rozšíření, která byla publikována na webu Visual Studio Marketplace, najdete v tématu [jak: Aktualizovat rozšíření](../extensibility/how-to-update-a-visual-studio-extension.md).

 Můžete nastavit rozšíření pro podporu více verzí sady Visual Studio. Další informace najdete v tématu [podporuje více verzí sady Visual Studio](../extensibility/supporting-multiple-versions-of-visual-studio.md).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Začínáme se šablonou projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md)|Vysvětluje, jak nainstalovat vlastní šablonu projektu pomocí šablony projektu VSIX.|
|[Anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md)|Popisuje součásti balíčku VSIX.|
|[Šablona projektu VSIX](../extensibility/vsix-project-template.md)|Obsahuje podrobné pokyny o tom, jak zabalit a publikovat rozšíření.|
|[Lokalizace balíčků VSIX](../extensibility/localizing-vsix-packages.md)|Vysvětluje, jak zajistit lokalizovaný text pro proces instalace pomocí extension.vsixlangpack soubory.|
|[Postupy: Aktualizace rozšíření](../extensibility/how-to-update-a-visual-studio-extension.md)|Popisuje postup aktualizace rozšíření ve vašem systému a jak nasadit aktualizace do existujícího rozšíření sady Visual Studio.|
|[Postupy: Přidání závislosti k balíčku VSIX](../extensibility/how-to-add-a-dependency-to-a-vsix-package.md)|Popisuje, jak přidat odkazy na balíčky VSIX pro nasazení.|
|[Příprava rozšíření pro nasazení Instalační služby systému Windows](../extensibility/preparing-extensions-for-windows-installer-deployment.md)|Vysvětluje, jak nasazení vašeho rozšíření Instalační služby systému Windows.|
|[Podepisování balíčků VSIX](../extensibility/signing-vsix-packages.md)|Vysvětluje, jak k podepisování balíčků VSIX.|
|[Privátní galerie](../extensibility/private-galleries.md)|Vysvětluje, jak vytvořit privátní Galerie rozšíření.|
|[Podpora více verzí sady Visual Studio](../extensibility/supporting-multiple-versions-of-visual-studio.md)|Ukazuje, jak mají vaše rozšíření podpory více verzí sady Visual Studio.|
|[Vyhledání sady Visual Studio](locating-visual-studio.md)|Popisuje, jak najít instancí sady Visual Studio k nasazení vlastních rozšíření.|
