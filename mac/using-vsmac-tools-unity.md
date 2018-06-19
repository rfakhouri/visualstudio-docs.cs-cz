---
title: Pomocí sady Visual Studio pro Mac Tools for Unity
description: Tato příručka popisuje, jak pomocí sady Visual Studio pro Mac nástroje pro rozšíření Unity
author: dantogno
ms.author: v-davian
ms.date: 07/17/2017
ms.assetid: 83FDD7A3-5D16-4B4B-9080-078E3FB5C623
ms.openlocfilehash: ab605b3a8505ac189bc0f628b717c6863f9fd902
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2018
ms.locfileid: "34454512"
---
# <a name="using-visual-studio-for-mac-tools-for-unity"></a>Pomocí sady Visual Studio pro Mac Tools for Unity

V této části dozvíte, jak používat Visual Studio pro Mac nástroje pro integrace a funkce produktivitu na Unity a použití sady Visual Studio pro Mac ladicí program pro vývoj Unity.

## <a name="opening-unity-scripts-in-visual-studio-for-mac"></a>Otevření Unity skripty v sadě Visual Studio pro Mac

Jakmile je Visual Studio pro Mac [nastavit jako editor externího skriptu pro Unity](setup-vsmac-tools-unity.md#configure-unity-for-use-with-visual-studio-for-mac), spuštění všech skriptů z editoru Unity automaticky spustí nebo přepínač tak, aby Visual Studio pro Mac, pomocí skriptu pro zvolený otevřete.

Alternativně můžete otevřít Visual Studio pro Mac se žádný skript otevřete v editoru zdrojového výběrem **otevření projektu C#** z **prostředky** nabídky v Unity.

![Otevřete projekt C#](media/using-vsmac-tools-unity-image1.png)

## <a name="unity-documentation-access"></a>Přístup k dokumentaci Unity

Visual Studio pro Mac Tools for Unity obsahuje zástupce pro přístup k dokumentaci rozhraní Unity API. Chcete-li získat přístup k dokumentaci k rozhraní API Unity ze sady Visual Studio pro Mac, umístěte kurzor přes rozhraní API Unity chcete další informace o a stiskněte klávesu **⌘ příkaz + '**.

## <a name="intellisense-for-unity-messages"></a>IntelliSense pro Unity zprávy
Modul Unity všesměrově zpráv, které mají MonoBehaviour skripty, které umožňuje vývojářům psát kód, který reaguje na zprávy například StisknutiMysi, OnTriggerEnter atd. Protože tyto nejsou virtuální metody v základní třídě MonoBehaviour, chybí některé integrovaného vývojového prostředí, jako je například MonoDevelop funkce doplňování kódu pro Unity zprávy.

Visual Studio pro Mac Tools for Unity však rozšiřuje jeho funkci technologie IntelliSense pro Unity zprávy. To usnadňuje implementaci Unity zprávy ve skriptech MonoBehaviour a pomáhá zajistit s learning Unity API. Použití technologie IntelliSense pro Unity zprávy:

1.  Umístěte kurzor na nový řádek uvnitř těla Třída odvozená z MonoBehaviour.

2.  Začátek zadáním názvu Unity zprávy, jako například `OnTriggerEnter`.

3.  Jednou písmena "**ovolit**" jste zadali, se zobrazí seznam IntelliSense návrhy.

  ![Používání atributu IntelliSense](media/using-vsmac-tools-unity-image2.png)

4.  Výběr v seznamu lze změnit třemi způsoby:

    * Pomocí **až** a **dolů** klávesy se šipkami.

    * Kliknutím myší na požadovanou položku.

    * Pokračováním zadejte název požadované položky.

5.  IntelliSense můžete vložit vybrané Unity zprávy, včetně všechny potřebné parametry:

    * Stisknutím kombinace kláves **kartě**.

    * Stisknutím kombinace kláves **vrátit**.

    * Poklepáním na vybranou položku.

  ![Vložit zprávu Unity z IntelliSense](media/using-vsmac-tools-unity-image3.png)

## <a name="adding-new-unity-files-and-folders"></a>Přidávání nových Unity souborů a složek

Když na projekt Unity v editoru Unity můžete vždy přidat nové soubory, Visual Studio pro Mac umožňuje snadno vytváření nové skripty Unity, shadery a složky z Visual Studia.

### <a name="add-a-new-c-monobehaviour-script"></a>Přidat nový skript MonoBehaviour C#

Chcete-li přidat nový skript jazyka C# MonoBehaviour **klikněte pravým tlačítkem na složku prostředky** nebo jeden z jejích podadresářů v řešení pro a vyberte **Přidat > Nový MonoBehaviour**.

![Přidat nové MonoBehaviour](media/using-vsmac-tools-unity-image4.png)

### <a name="add-a-new-unity-shader"></a>Přidat nové shaderu Unity

Chcete-li přidat nový shaderu Unity, **klikněte pravým tlačítkem na složku prostředky** nebo podadresáře v řešení pro a vyberte **Přidat -> Nový shaderu**.

### <a name="add-a-new-folder"></a>Přidejte novou složku

Chcete-li přidat novou složku, **klikněte pravým tlačítkem na složku prostředky** nebo podadresáře v řešení pro a vyberte **Přidat > novou složku**.

Tyto doplňky se projeví v projektu okna editoru Unity.

### <a name="to-rename-a-file-or-folder"></a>Přejmenování souboru nebo složky
**Klikněte pravým tlačítkem na** na položku, kterou chcete přejmenovat v řešení odsadí a vyberte **přejmenovat...** .

> [!NOTE]
> Pokud máte nový projekt Unity s žádné skripty a složce prostředky nezobrazuje v panelu pro řešení v sadě Visual Studio pro Mac, přidejte počáteční C# skript v editoru Unity.

## <a name="unity-debugging"></a>Ladění Unity

Projekty Unity můžete ladit pomocí sady Visual Studio for Mac.

### <a name="start-debugging"></a>Spuštění ladění

Spustit ladění:

1.  Připojit Visual Studio k Unity kliknutím **přehrání** tlačítko nebo typ **příkaz + vrátit**, nebo **F5**.

  ![Kliknutím na tlačítko Přehrát v sadě Visual Studio](media/using-vsmac-tools-unity-image5.png)

2.  Přepnout na Unity a klikněte na **přehrání** tlačítko spustit hru v editoru.

  ![Kliknutím na tlačítko Přehrát v Unity](media/using-vsmac-tools-unity-image6.png)

3.  Pokud hra běží v editoru Unity během připojení k sadě Visual Studio, bude žádné zarážky došlo k pozastavení provádění hry a vyvolat řádkem kódu, kde hra dosáhl zarážek v sadě Visual Studio for Mac.

### <a name="stop-debugging"></a>Zastavte ladění

Aby se ukončilo ladění:

1.  Klikněte **Zastavit** v sadě Visual Studio pro Mac, nebo stiskněte tlačítko **stisknutím klávesy Shift + příkazu a vrátit**.

  ![Klikněte na příkaz Zastavit v sadě Visual Studio](media/using-vsmac-tools-unity-image7.png)

Další informace o ladění v sadě Visual Studio pro Mac, najdete v části [používání ladicího programu](https://docs.microsoft.com/visualstudio/mac/debugging).
