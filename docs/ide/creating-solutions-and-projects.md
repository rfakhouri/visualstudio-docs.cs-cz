---
title: "Vytvoření řešení a projektů v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 06/16/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.openprojectfromweb
- vs.newproject
- VS.ToolsOptionsPages.Projects.General
- SolutionItemsProject
helpviewer_keywords:
- solutions [Visual Studio], deleting
- solutions [Visual Studio], creating
- projects [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4a4afda7895f1faf491da09b26ebe265196eece2
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="create-solutions-and-projects"></a>Vytvoření řešení a projekty

*Projekty* jsou logické kontejnery v sadě Visual Studio, který obsahovat položky potřebné k vytvoření aplikace, jako jsou například soubory zdrojového kódu, rastrové obrázky, ikony a odkazů na součásti a služeb. Když vytvoříte nový projekt, Visual Studio vytvoří *řešení* tak, aby obsahovala projektu. Pokud chcete, můžete přidat pak další nové nebo existující projekty k řešení. Řešení může také obsahovat soubory, které nejsou připojené k žádné konkrétní projekt.

![Hierarchie řešení nebo projektu](./media/vside-proj-soln.png)

Projekty a řešení můžete zobrazit v okně nástroje názvem **Průzkumníku řešení**. Následující snímek obrazovky ukazuje příklad řešení v Průzkumníku řešení (BikeSharing.Xamarin-UWP), který obsahuje dva projekty: BikeSharing.Clients.Core a BikeSharing.Clients.Windows. Každý projekt obsahuje více souborů, složek a odkazy. Název projektu tučným písmem je *spouštěný projekt*; to znamená, projekt, který se spustí při spuštění aplikace. Můžete určit, který projekt je projekt po spuštění.

![Průzkumník řešení se projekty](./media/vside-solution-explorer-projects.png)

Zatímco můžete vytvořit projekt sami přidáním potřebné soubory, Visual Studio nabízí výběr šablon projektu tak, abyste získali počáteční head. Vytvoření nového projektu z šablony získáte projekt se základní vlastnosti pro tento typ projektu, a můžete přejmenovat soubory nebo k němu podle potřeby přidat nové nebo stávající kód a dalším prostředkům.

Který výše uvedeného, projekty a řešení není nutné vývoj aplikací v sadě Visual Studio. Můžete otevřít také pouze kód, který jste naklonovali z Git nebo stáhnout jinde. Další informace najdete v tématu [vývoj kódu v sadě Visual Studio bez projekty a řešení](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md).

> [!NOTE]
> Popisy v tomto tématu jsou založené na Visual Studio Community edition. Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch zde popsaných v závislosti na vašem nastavení nebo verzi systému Visual Studio. Chcete-li změnit nastavení, například k **Obecné** nebo **Visual C++** nastavení, vyberte **nástroje**, **nastavení importu a exportu**a potom Zvolte **obnovit nastavení**.

## <a name="to-create-a-project-from-a-project-template"></a>Vytvoření projektu ze šablony projektu

1. Chcete-li vytvořit nový projekt v sadě Visual Studio několika způsoby. Na stránce Start zadejte název šablony projektu v **vyhledávání šablony projektů** pole, nebo zvolte **vytvořit nový projekt** odkazu k otevření **nový projekt** dialogové okno. Můžete také **soubor**, **nový**, **projektu...**  v nabídce panelu, nebo zvolte **nový projekt** tlačítka na panelu nástrojů.

  ![Úvodní stránka](./media/vside-newproject1.png)

  V **nový projekt** dialogové okno, šablony dostupné projektu se zobrazí v seznamu v části **šablony** kategorie. Šablony jsou uspořádány podle programovacího jazyka a typu projektu, například Visual C#, JavaScript a Azure Data Lake.

  ![Dialogové okno Nový projekt](./media/vside-newproject-templates-list.png)

  > [!NOTE]
  > Ze seznamu dostupných jazyků a šablony projektu, který se zobrazí závisí na verzi Visual Studio používáte a úlohy, které jsou nainstalovány. Další informace o tom, jak nainstalovat další úlohy najdete v tématu [upravit Visual Studio 2017 přidáním nebo odebráním úlohy a součásti](../install/modify-visual-studio.md).

1. Zobrazit seznam šablon pro programovací jazyk, který chcete použít tak, že zvolíte trojúhelníček vedle název jazyka a poté zvolte typ projektu.

  Následující příklad ukazuje šablon projektu, který je k dispozici pro webové projekty Visual C#.

  ![Šablony projektů](./media/vside-newproject-projects-list.png)

1. Zadejte název pro nový projekt v **název** pole. Můžete uložit projektu ve výchozím umístění ve vašem systému, nebo zvolte **Procházet** tlačítko Najít jiné umístění.

  Volitelně můžete změnit název řešení nebo přidat nový projekt do úložiště Git výběrem **přidat do správy zdrojového kódu**.

1. Vyberte **OK** tlačítko pro vytvoření řešení a projektu.

1. Pokud chcete do řešení přidat další projekt, vyberte uzel řešení v Průzkumníku řešení a potom na panelu nabídek vyberte **projektu**, **přidat novou položku**.

## <a name="create-a-project-from-existing-code-files"></a>Vytvoření projektu z existujících souborů kódu

Pokud máte kolekci soubory zdrojového kódu, můžete je snadno přidat k projektu.

1. V nabídce zvolte **soubor**, **nový**, **projekt z existujícího kódu**.

1. V **vytvoření projektu z existujících souborů kódu** průvodce, zvolte typ projektu, které mají být v **jaký typ projektu chcete vytvořit?** rozevíracího seznamu pole a potom vyberte **další**  tlačítko.

1. V průvodci, přejděte do umístění souborů a potom zadejte název pro nový projekt v **název** pole. Až skončíte, zvolte **Dokončit** tlačítko.

> [!NOTE]
> Tato možnost je nejvhodnější pro poměrně jednoduché kolekce souborů. V současné době jsou podporovány pouze typy projektů Visual C++, Apache Cordova, Visual Basic a Visual C#.

## <a name="add-files-to-a-solution"></a>Přidání souborů do řešení

Pokud máte soubor, který se vztahuje na více projektů, jako je soubor readme pro řešení, nebo jiné soubory, které logicky patří na úrovni řešení spíše než v rámci konkrétní projekt, pak můžete přidat je do řešení sám sebe. Postup přidání položky do řešení, v nabídce kontextu (klikněte pravým tlačítkem) uzlu řešení v **Průzkumníku řešení**, zvolte **přidat**, **nová položka**, nebo **přidat**, **Existující položka**.

## <a name="create-a-net-project-that-targets-a-specific-version-of-the-net-framework"></a>Vytvoření projektu rozhraní .NET, která je cílena na konkrétní verzi rozhraní .NET Framework

Když vytvoříte projekt, můžete zadat konkrétní verzi rozhraní .NET Framework, který chcete projekt, který používá. K určení verze rozhraní .NET framework, vyberte **rozhraní .NET Framework** verze rozevírací nabídky v **nový projekt** dialogové okno.

![Selektor verze rozhraní .NET framework](./media/vside-newproject-framework.png)

> [!NOTE]
> Pokud vytváříte projekt ze šablony .NET Core, verzi rozhraní .NET Framework, kterou vyberete v rozevíracím seznamu se ignoruje.

> [!TIP]
> Pokud jste nastavili verzi rozhraní .NET Framework před výběrem šablony projektu, pak Visual Studio se zobrazí, jen šablony, které jsou kompatibilní s danou verzi rozhraní .NET Framework.

Musíte mít rozhraní .NET Framework 3.5 v systému nainstalovány pro přístup k rozhraní .NET Framework verze starší než rozhraní .NET Framework 4.

## <a name="create-empty-solutions"></a>Vytvořit prázdný řešení

Můžete také vytvořit prázdný řešení, které mají žádné projekty. To může být vhodnější než v případech, kde chcete vytvořit řešení a projekty od začátku.

### <a name="to-create-an-empty-solution"></a>Vytvoření prázdného řešení

1. V nabídce zvolte **soubor**, **nový**, **projektu...** .

1. V levém (**šablony**) podokně vyberte **jiné typy projektů**, **řešení sady Visual Studio** v seznamu rozšířené.

1. V prostředním podokně vyberte **prázdného řešení**.

1. Zadejte **název** a **umístění** hodnoty pro vaše řešení, zvolte **OK**.

Po vytvoření prázdného řešení, můžete přidat nové nebo existující projekty nebo položky k němu výběrem **přidat novou položku** nebo **přidat existující položku** na **projektu** nabídky.

Jak už bylo zmíněno dříve, můžete také otevřít soubory kódu bez nutnosti projekt nebo řešení. Další informace o vývoji kód tímto způsobem najdete v tématu [vývoj kódu v sadě Visual Studio bez projekty a řešení](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md).

## <a name="create-a-temporary-project-c-and-visual-basic"></a>Vytvoření dočasné projektu (C# a Visual Basic)

Pokud vytvoříte. Na základě NET projekt bez zadání umístění na disku, je dočasný projekt. Dočasné projekty umožňují experimentovat s projekty rozhraní .NET. Kdykoliv při práci s projektem dočasné, můžete ho uložte nebo zahoďte ho.

Chcete-li vytvořit dočasný projekt, nejprve přejděte na **nástroje**, **možnosti**, **projekty a řešení**, **Obecné**a zrušte zaškrtnutí políčka **Uložit nové projekty při vytvoření** zaškrtávací políčko. Otevřete **nový projekt** dialogu jako obvykle.

## <a name="delete-a-solution-project-or-item"></a>Odstranit řešení, projekt nebo položky

Řešení a jejich obsah můžete odstranit trvale, ale nikoli pomocí prostředí Visual Studio IDE. Odstraňování položek v sadě Visual Studio pouze odebere z aktuální řešení nebo projektu. Pokud chcete trvale odstranit z vašeho systému řešení nebo jiné součásti, pomocí Průzkumníka souborů můžete odstranit složku, která obsahuje soubory .sln a .suo řešení. Před odstraněním trvale řešení, ale doporučujeme zálohovat všechny projekty nebo souborů v případě potřeby znovu.

> [!NOTE]
> Soubor .suo je skrytý soubor, který se nezobrazí ve výchozím nastavení Průzkumníka souborů. K zobrazení skrytých souborů na **zobrazení** nabídky v Průzkumníku souborů, vyberte **skryté položky** zaškrtávací políčko.

### <a name="to-permanently-delete-a-solution"></a>Trvale odstranit řešení

1. V **Průzkumníku řešení**, v místní nabídce řešení, které chcete odstranit, zvolte **otevřít složku v Průzkumníku souborů**.

1. V Průzkumníku souborů přejděte o jednu úroveň výše.

1. Zvolte složku obsahující řešení a pak **odstranit** klíč.

## <a name="see-also"></a>Viz také

[Projekty a řešení](../ide/solutions-and-projects-in-visual-studio.md)  
[Úložiště s otevřeným zdrojem společnosti Microsoft na Githubu](https://github.com/Microsoft)  
[Ukázky sady Visual Studio](../ide/visual-studio-samples.md)  
[Ukázky kódu vývojáře](https://code.msdn.microsoft.com/)  
