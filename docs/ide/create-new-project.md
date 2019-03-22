---
title: Vytvoření nového projektu
ms.date: 03/19/2019
ms.topic: conceptual
f1_keywords:
- vs.newproject
helpviewer_keywords:
- projects [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9f5d48ee97e1e0d92237fe5836c8bd9c1888c3a4
ms.sourcegitcommit: 3201da3499051768ab59f492699a9049cbc5c3c6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58355244"
---
# <a name="create-a-new-project-in-visual-studio"></a>Vytvoření nového projektu v sadě Visual Studio

::: moniker range="vs-2017"

## <a name="open-the-new-project-dialog"></a>Otevřete dialogové okno Nový projekt

Existuje několik způsobů, jak vytvořit nový projekt v sadě Visual Studio 2017. Na úvodní stránce můžete zadat název šablony projektu v **Hledat šablony projektů** pole nebo klikněte **vytvořit nový projekt** odkaz k otevření **nový projekt** dialogového okna pole. Kromě úvodní stránku, můžete také zvolit **souboru** > **nový** > **projektu** na řádku nabídek nebo kliknutím **nový projekt**  tlačítko na panelu nástrojů.

![Úvodní stránka a soubor > Nový > Projekt](./media/vside-newproject1.png)

## <a name="select-a-template-type"></a>Vyberte typ šablony

V **nový projekt** dialogovém okně dostupných šablon projektu se zobrazí v seznamu v části **šablony** kategorie. Šablony jsou uspořádané podle programovacího jazyka a projekt typu, jako je vizuál C#, JavaScript a Azure Data Lake.

![Dialogové okno Nový projekt](./media/vside-newproject-templates-list.png)

> [!NOTE]
> Seznam dostupných jazyků a šablony projektů, které se zobrazí, závisí na verzi sady Visual Studio spustíte a úlohy, které jsou nainstalovány. Další informace o tom, jak nainstalovat další úlohy, naleznete v tématu [upravit přidáním nebo odebráním úlohy a komponenty Visual Studio](../install/modify-visual-studio.md).

Zobrazte seznam šablon pro programovací jazyk, který chcete použít klepnutím na tlačítko trojúhelníku vedle názvu jazyka a následným výběrem kategorie projektu (například Windows Desktop).

Následující obrázek ukazuje dostupné šablony projektů pro vizuál C# projekty .NET Core:

![Šablony projektů](./media/new-project-dialog-net-core.png)

## <a name="configure-your-project"></a>Konfigurace projektu

Zadejte název nového projektu v **název** pole. Projekt můžete uložit ve výchozím umístění v počítači nebo kliknutím **Procházet** tlačítko a vyhledejte jiné umístění. Můžete také zvolit řešení nebo přidat nový projekt do úložiště Git (výběrem **přidat do správy zdrojových kódů**).

Klikněte na tlačítko **OK** k vytváření řešení a projektu.

::: moniker-end

::: moniker range=">=vs-2019"

## <a name="open-the-create-a-new-project-page"></a>Otevřete vytvořit nová stránka projektu

Vytvoření nového projektu v aplikaci Visual Studio 2019 několika způsoby. Při prvním otevření sady Visual Studio, zobrazí se okno start a z něj, můžete použít **vytvořte nový projekt**.

![Vytvoření nového projektu z okna spuštění v VS 2019](media/vs-2019/start-window-create-new-project.png)

Pokud vývojovém prostředí sady Visual Studio je už otevřená, můžete vytvořit nový projekt výběrem **souboru** > **nový** > **projektu** na v nabídce panelu nebo kliknutím **nový projekt** tlačítko na panelu nástrojů.

![Tlačítko Nový projekt v aplikaci Visual Studio 2019](media/vs-2019/new-project-button.png)

## <a name="select-a-template-type"></a>Vyberte typ šablony

Na **vytvořte nový projekt** stránce, na levé straně se zobrazí seznam nedávno vybrané šablony. Šablony jsou seřazeny podle *naposledy použitých*.

Pokud nejsou výběrem z naposledy použitých šablon, můžete filtrovat všech dostupných šablon projektu podle **jazyk** (například C# nebo C++), **platformy** (například Windows nebo Azure), a **Typ projektu** (například Desktop nebo Web). Můžete také zadat hledaný text do vyhledávacího pole filtrovat další šablony, například **asp.net**.

![Filtry šablony projektu ve Visual Studio 2019](media/vs-2019/create-new-project-filters.png)

Značky, které se zobrazí v rámci každé šablony odpovídají tří rozevírací seznam filtrů (jazyk, platformu a projekt typu).

> [!TIP]
> Pokud nevidíte šablonu, kterou hledáte, je pravděpodobně chybí úloh pro Visual Studio. Chcete-li nainstalovat další úlohy, například **vývoj pro Azure** nebo **vývoj mobilních aplikací pomocí .NET**, klikněte na tlačítko **nainstalovat další nástroje a funkce** odkaz k otevření Vizuálu Instalační program sady Studio. Tam pak vyberete úlohy, které chcete nainstalovat, a klikněte na tlačítko **změnit**. Poté bude k dispozici lze vybírat další projekt šablony.
>
> ![Odkaz na další nástroje a funkce nainstalovat VS 2019](media/vs-2019/install-more-tools-features.png)

Vyberte šablonu a potom klikněte na tlačítko **Další**.

## <a name="configure-your-project"></a>Konfigurace projektu

**Konfigurovat nový projekt** stránka obsahuje možnosti, jak název vašeho projektu (a řešení), vyberte umístění na disku a vyberte verzi rozhraní Framework (Pokud je k dispozici v šabloně zvolíte).

![Konfigurovat vaše nová stránka projektu v VS 2019](media/vs-2019/configure-new-project.png)

> [!NOTE]
> Pokud vytvoříte nový projekt, pokud již máte projekt nebo řešení otevřít v sadě Visual Studio, je k dispozici možnost Další konfiguraci. Můžete vytvořit nové řešení nebo přidat nový projekt do řešení, které je již otevřen.
>
> ![Vytvoření nového řešení nebo přidat do existujícího řešení v VS 2019](media/vs-2019/configure-new-project-solution.png)

Klikněte na tlačítko **vytvořit** vytvoříte nový projekt.

::: moniker-end

## <a name="add-additional-projects-to-a-solution"></a>Přidat další projekty do řešení

Pokud chcete přidat další projekt do řešení, klikněte pravým tlačítkem na uzel řešení v **Průzkumníka řešení** a zvolte **přidat** > **nový projekt**.

## <a name="see-also"></a>Viz také:

- [Vytváření řešení a projektů](creating-solutions-and-projects.md)
