---
title: 'Kurz: Otevření projektu z úložiště'
description: Zjistěte, jak pomocí sady Visual Studio otevřete projekt v úložišti Git nebo Azure DevOps.
ms.custom: get-started
ms.date: 03/30/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: tutorial
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7fbea3fe7599bf1fc970f5fa77841a395bc5419b
ms.sourcegitcommit: d4bea2867a4f0c3b044fd334a54407c0fe87f9e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58790651"
---
# <a name="tutorial-open-a-project-from-a-repo"></a>Kurz: Otevření projektu z úložiště

V tomto kurzu budete používat Visual Studio pro připojení k úložišti poprvé a pak otevřete projekt z něj.

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+rc) stránku a nainstalovat zdarma.

::: moniker-end

## <a name="open-a-project-from-a-github-repo"></a>Otevřete projekt z úložiště GitHub

::: moniker range="vs-2017"

1. Otevřete Visual Studio 2017.

1. V horní nabídce zvolte **souboru** > **otevřít** > **otevřít ze správy zdrojových kódů**.

   **Team Explorer – připojit** se otevře podokno.

    ![V okně Průzkumník týmových projektů v integrovaném vývojovém prostředí sady Visual Studio](./media/open-proj-repo-team-explorer.png)

1. V **místní úložiště Git** zvolte **klonování**.

    ![Zvolením možnosti klonovat z části místní úložiště Git](./media/open-proj-repo-local-git-repo-clone.png)

1. Do pole, které se říká ***zadejte adresu URL úložiště Git pro klonování***, zadejte nebo vložte adresu URL pro úložiště a potom stiskněte klávesu **Enter**. (Může se zobrazit výzva k přihlášení na Githubu a pokud ano, Uděláte to tak.)

   Po sady Visual Studio duplicity úložišti, Průzkumník týmových projektů zavře a otevře se Průzkumník řešení. Zobrazí se zpráva s upozorněním *klikněte na řešení a složky výše, chcete-li zobrazit seznam řešení*. Zvolte **řešení a složky**.

   ![Z Průzkumníku řešení zvolte "Řešení a složky"](./media/open-proj-repo-github-solutions-folders.png)

1. Pokud máte k dispozici soubor řešení, se zobrazí v rozevírací nabídce "Řešení a složky". Zvolte jej a Visual Studio otevře vaše řešení.

   ![Zvolte, co chcete otevřít z rozevíracího seznamu Průzkumníka řešení](./media/open-proj-repo-github-solutions-folders-picker.png)

   Pokud nemáte soubor řešení (konkrétně soubor .sln) ve vašem úložišti, rozevírací nabídce se Řekněme, že "Nalezeno žádné řešení." Můžete však poklepejte na libovolný soubor v nabídce složku ji otevřete v editoru kódu sady Visual Studio.

### <a name="review-your-work"></a>Projděte si svou práci

Zobrazte následující animace zkontrolovat práci, kterou jste dokončili v předchozí části.

   ![Animace dvojice v otevření projektu v úložišti GitHub s použitím sady Visual Studio](./media/open-project-from-github.gif)

::: moniker-end

::: moniker range="vs-2019"

1. Open Visual Studio 2019.

1. V okně start zvolte **klonování nebo prohlédněte si kód**.

   ![Zobrazit okno 'vytvořte nový projekt.](../get-started/media/vs-2019/clone-checkout-code-dark.png)

1. Zadejte nebo zadejte umístění úložiště a pak zvolte **klonování**.

   ![Zobrazení okna kódu klonování nebo rezervace](../get-started/media/vs-2019/clone-checkout-code-git-repo-dark.png)

   Visual Studio otevřete projekt z úložiště.

1. Pokud máte k dispozici soubor řešení, se zobrazí v rozevírací nabídce "Řešení a složky". Zvolte jej a Visual Studio otevře vaše řešení.

   ![Zvolte, co chcete otevřít z rozevíracího seznamu Průzkumníka řešení](./media/open-proj-repo-github-solutions-folders-picker.png)

   Pokud nemáte soubor řešení (konkrétně soubor .sln) ve vašem úložišti, rozevírací nabídce se Řekněme, že "Nalezeno žádné řešení." Můžete však poklepejte na libovolný soubor v nabídce složku ji otevřete v editoru kódu sady Visual Studio.

::: moniker-end

## <a name="open-a-project-from-an-azure-devops-repo"></a>Otevření projektu ze úložiště Azure DevOps

::: moniker range="vs-2017"

1. Otevřete Visual Studio 2017.

1. V horní nabídce zvolte **souboru** > **otevřít** > **otevřít ze správy zdrojových kódů**.

   **Team Explorer – připojit** se otevře podokno.

    ![V okně Průzkumník týmových projektů v integrovaném vývojovém prostředí sady Visual Studio](./media/open-proj-repo-team-explorer.png)

1. Tady jsou dva způsoby, jak se připojit k úložišti Azure DevOps:

      - V **poskytovatelé hostovaných služeb** zvolte **připojit...** .

        ![Poskytovatelé hostovaných služeb části okna Průzkumníka týmových projektů v integrovaném vývojovém prostředí sady Visual Studio](./media/open-proj-repo-azure-devops.png)

      - V **spravovat připojení** rozevíracím seznamu klikněte na položku **připojit do projektu...** .

        ![Spravovat připojení části okna Průzkumníka týmových projektů v integrovaném vývojovém prostředí sady Visual Studio](./media/open-proj-repo-azuredevops-manage-connections.png)

1. V **připojit k projektu** dialogové okno Vyberte úložiště, který chcete připojit a klikněte na tlačítko **klonování**.

      !["Připojení k dialogovém okně projekt", který je generován ze sady Visual Studio](./media/open-proj-azure-devops-connect-cloud-clone.png)

    > [!NOTE]
    > Co se zobrazí v seznamu, závisí na úložiště Azure DevOps, které máte přístup k.

1. Po sady Visual Studio duplicity úložišti, Průzkumník týmových projektů zavře a otevře se Průzkumník řešení. Zobrazí se zpráva s upozorněním *klikněte na řešení a složky výše, chcete-li zobrazit seznam řešení*. Zvolte **řešení a složky**.

      !["Řešení a složky" oznámení z Průzkumníka týmových projektů v sadě Visual Studio](./media/open-proj-repo-solutions-folders.png)

   Soubor řešení (konkrétně soubor .sln), se zobrazí v rozevírací nabídce "Řešení a složky". Zvolte jej a Visual Studio otevře vaše řešení.

   Pokud nemáte soubor řešení ve vašem úložišti, se dozvíte rozevírací nabídce "Řešení nebyl nalezen žádný". Můžete však poklepejte na libovolný soubor v nabídce složku ji otevřete v editoru kódu sady Visual Studio.

::: moniker-end

::: moniker range="vs-2019"

1. Open Visual Studio 2019.

1. V okně start zvolte **klonování nebo prohlédněte si kód**.

   ![Zobrazit okno 'vytvořte nový projekt.](../get-started/media/vs-2019/clone-checkout-code-dark.png)

1. V **procházet úložiště** zvolte **Azure DevOps**.

   ![Zobrazit okno 'klonování nebo prohlédněte si kód.](../get-started/media/vs-2019/clone-checkout-code-git-repo-dark.png)

   Pokud se zobrazí okno přihlášení, přihlaste se ke svému účtu.

1. V **připojit k projektu** dialogové okno Vyberte úložiště, který chcete připojit a klikněte na tlačítko **klonování**.

      !["Připojení k dialogovém okně projekt", který je generován ze sady Visual Studio](./media/open-proj-azure-devops-connect-cloud-clone.png)

    > [!NOTE]
    > Co se zobrazí v seznamu, závisí na úložiště Azure DevOps, které máte přístup k.

   Visual Studio otevře **Team Exploreru** a po dokončení klonování se zobrazí oznámení.

     ![Okno Průzkumníku týmových projektů v sadě Visual Studio po dokončení klonování](./media/vs-2019/clone-complete-azure-devops.png)

1. Chcete-li zobrazit složek a souborů, zvolte **zobrazit zobrazení složky** odkaz.

     ![Část řešení pro okno Průzkumníku týmových projektů v sadě Visual Studio po dokončení klonování](./media/vs-2019/show-folder-view-azure-devops.png)

     Visual Studio otevře **Průzkumníka řešení**.

1. Zvolte **řešení a složky** odkazu pro vyhledávání a otevřete soubor řešení (konkrétně soubor .sln).

      !["Řešení a složky" oznámení z Průzkumníka týmových projektů v sadě Visual Studio](./media/open-proj-repo-solutions-folders.png)

   Pokud nemáte soubor řešení ve vašem úložišti, zobrazí se zpráva "Řešení nebyl nalezen žádný". Můžete však poklepejte na libovolný soubor v nabídce složku ji otevřete v editoru kódu sady Visual Studio.

::: moniker-end

## <a name="next-steps"></a>Další kroky

Pokud jste připraveni kódu pomocí sady Visual Studio, Ponořte se do libovolného z následujících kurzů specifické pro jazyk:

- [Visual Studio tutorials | **C#**](./csharp/index.yml)
- [Visual Studio tutorials | **Visual Basic**](./visual-basic/index.yml)
- [Visual Studio kurzy | **C++**](/cpp/get-started/)
- [Visual Studio tutorials | **Python**](/visualstudio/python/)
- [Visual Studio kurzy | **JavaScript**, **TypeScript**, a **Node.js**](/visualstudio/javascript/)

## <a name="see-also"></a>Viz také:

- [Azure DevOps služby: Začínáme s úložišti Azure a Visual Studio](/azure/devops/repos/git/gitquickstart/)
- [Microsoft Learn: Začínáme s Azure DevOps](/learn/modules/get-started-with-devops/)