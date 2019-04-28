---
title: 'Kurz: Vytvoření webové aplikace ASP.NET Core s Entity Framework a Visual Studio 2019'
titleSuffix: ''
description: Jako první krok před vytvořením webové aplikace ASP.NET Core zjistěte, jak nainstalovat Visual Studio 2019 s touto Výukové video a podrobné pokyny.
ms.custom: get-started
ms.date: 03/31/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
monikerRange: vs-2019
ms.topic: tutorial
ms.devlang: CSharp
author: ardalis
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 711082c70c6174bdf3363ddb12d233ceb3f78f0d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838932"
---
# <a name="tutorial-create-your-first-aspnet-core-app-using-entity-framework-with-visual-studio-2019"></a>Kurz: Vytvoření první aplikace v ASP.NET Core s Visual Studio 2019 používající nástroj Entity Framework

V tomto kurzu vytvoříte webové aplikace ASP.NET Core, který používá data a nasaďte ji do Azure. V tomto kurzu se skládá z následujících kroků:

- [Krok 1: Install Visual Studio 2019](#step-1-install-visual-studio-2019)
- [Krok 2: Vytvoření vaší první webové aplikace ASP.NET Core](tutorial-aspnet-core-ef-step-02.md)
- [Krok 3: Práce s daty pomocí Entity Frameworku](tutorial-aspnet-core-ef-step-03.md)
- [Krok 4: Vystavení webového rozhraní API z aplikace ASP.NET Core](tutorial-aspnet-core-ef-step-04.md)
- [Krok 5: Nasazení aplikace ASP.NET Core do Azure](tutorial-aspnet-core-ef-step-05.md)

## <a name="step-1-install-visual-studio-2019"></a>Krok 1: Install Visual Studio 2019

Zjistěte, jak nainstalovat Visual Studio 2019 s touto Výukové video a podrobné pokyny. Pokud jste již nainstalovali Visual Studio, přeskočte k části [krok 2: Vytvoření vaší první webové aplikace ASP.NET Core](tutorial-aspnet-core-ef-step-02.md).

_Podívejte se na toto video a použijte k instalaci sady Visual Studio a vytvořte svoji první aplikaci ASP.NET Core._

> [!VIDEO https://www.youtube.com/embed/Fz_HAqQGLtY]

## <a name="download-the-installer"></a>Stažení instalačního programu

Přejděte na [visualstudio.com](https://visualstudio.com) najít instalační služby. Vyhledejte Visual Studio 2019 odkaz a klikněte na něj zahájíte stahování. Pro bezplatnou verzi sady Visual Studio zvolte Visual Studio Community.

## <a name="start-the-installer"></a>Spusťte instalační program

Až se stahování dokončí, klikněte na tlačítko **spustit** spuštění Instalační služby.

![Visual Studio 2019 Installer](media/vs-2019/vs2019-installer.png)

## <a name="choose-workloads"></a>Vybrat úlohy

Visual Studio lze použít pro různé druhy vývoje a úlohy usnadňují stáhnout vše, co potřebujete pro typ aplikace, které mají být sestaveny. Zvolte **technologie ASP.NET a Web Development** a **vývoj pro různé platformy .NET Core** úlohy nyní. Může vždy znovu spustit instalační program později k instalaci dalších úloh a součástí.

![Visual Studio 2019 Choose Workloads](media/vs-2019/vs2019-choose-workloads.png)

## <a name="install"></a>Instalace

Klikněte na tlačítko **nainstalovat** a nechat instalační program stáhnout a nainstalovat sadu Visual Studio.

## <a name="run-visual-studio-for-the-first-time"></a>Při prvním spuštění sady Visual Studio

Visual Studio by měl spustit automaticky po dokončení instalačního programu. Můžete být vyzváni k přihlášení, která má některé skvělé funkce související s ním, ale pro teď můžete k tomu později. Dále můžete nastavení motivu a vývoj. Jakmile jste provedli tyto možnosti, budete připravení začít svůj první projekt. Klikněte na tlačítko **vytvořte nový projekt** a klikněte na tlačítko **webové aplikace ASP.NET Core**.

![Visual Studio 2019 vytvořte nový projekt webové aplikace ASP.NET Core](media/vs-2019/vs2019-create-new-project.png)

## <a name="explore-aspnet-core-project-types"></a>Prozkoumejte typy projektů ASP.NET Core

Zvolte název projektu a umístění, a pak vyberte **vytvořit**. Nyní zvolte šablonu použít pro aplikace ASP.NET Core. Můžete použít jednu z následujících možností:

- Prázdný. Prázdná šablona projektu, který umožňuje začít úplně od začátku.
- API. Nejvhodnější pro webová rozhraní API.
- Webová aplikace. Standardní webová aplikace ASP.NET Core vytvořená se stránkami Razor.
- Webová aplikace (Model-View-Controller). Standardní webová aplikace ASP.NET Core pomocí vzor Model-View-Controller.
- Angular.
- React.js.
- React.js / Redux.
- Knihovny tříd Razor. Umožňuje sdílet prostředky Razor mezi projekty.

Všimněte si, že pro většinu šablony projektu můžete také povolit podporu Dockeru zaškrtnutím pole. Podpora ověřování můžete také přidat kliknutím na tlačítko pro ověření změn. Odtud můžete vybrat z:

- Bez ověřování.
- Individuální uživatelské účty. Tyto jsou uložené v databázi místních nebo založené na Azure.
- Pracovní nebo školní účty. Tato volba používá služby Active Directory, Azure AD nebo Office 365 pro ověřování.
- Ověřování Windows. Vhodný pro intranetové aplikace.

Vyberte standardní šablony webové aplikace bez ověřování a klikněte na tlačítko **OK**.

![Visual Studio 2019 Choose ASP.NET Core Project Options](media/vs-2019/vs2019-choose-aspnetcore-project.png)

## <a name="next-steps"></a>Další kroky

V dalším videu se dozvíte další informace o váš první projekt ASP.NET Core.

[Kurz: Vytvoření vaší první webové aplikace ASP.NET Core](tutorial-aspnet-core-ef-step-02.md)

## <a name="see-also"></a>Viz také:

- [Kurz: Začínáme s C# a ASP.NET Core](tutorial-aspnet-core.md) Podrobnější kurz bez na video s návodem
