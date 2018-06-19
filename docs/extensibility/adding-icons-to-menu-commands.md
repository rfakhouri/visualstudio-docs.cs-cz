---
title: Přidávání ikon na příkazy nabídky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- icons [Visual Studio], adding to toolbars
- toolbars [Visual Studio], adding icons to commands
- commands [Visual Studio], adding icons
ms.assetid: 362a0c7e-5729-4297-a83f-1aba1a37fd44
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8591c55a176493ace23df2de61ba26d58a3155e2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31098389"
---
# <a name="adding-icons-to-menu-commands"></a>Přidávání ikon na příkazy nabídky
Příkazy se může zobrazit na nabídek a panelů nástrojů. Na panely nástrojů je běžné pro příkaz pro zobrazí právě ikonu (a šetřit tak místo) při v nabídkách, že příkaz se obvykle zobrazují s jak ikonu a text.  
  
 Ikony jsou 16 × široké 16 pixelů vysoké a může být buď 8bitové barvy (256 barvami) nebo hloubku 32bitové barvy (true barvu). 32bitové barvy ikony jsou upřednostněny. Ikony jsou obvykle uspořádány do jednoho vodorovném řádku v jednom rastrového obrázku, i když jsou povoleny více bitmapy. Tento rastrový obrázek je deklarován v souboru .vsct společně s jednotlivé ikony, které jsou k dispozici v souboru bitové mapy. V tématu referenční informace pro [bitmap Element](../extensibility/bitmaps-element.md) další podrobnosti.  
  
## <a name="adding-an-icon-to-a-command"></a>Přidání ikonu k příkazu  
 Následující postup předpokládá, že máte existující projekt VSPackage pomocí příkazu v nabídce. Chcete-li zjistit, jak to provést, najdete v části [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
1.  Vytvoření rastrového obrázku hloubky barva 32 bitů. Ikona je vždy velikosti 16 x 16, takže tento rastrový obrázek musí být 16 pixelů a násobkem 16 pixelů.  
  
     Každá ikona je umístěn na rastrový obrázek vedle sebe na jednom řádku. Používá se k označení místech průhlednost v každá ikona alfa kanálu.  
  
     Pokud chcete použít hloubka 8bitové barvy, použijte purpurová, `RGB(255,0,255)`, jako průhlednost. 32bitové barvy ikony jsou však upřednostňované.  
  
2.  Zkopírujte soubor ikony do adresáře prostředků ve vašem projektu VSPackage. V Průzkumníku řešení přidejte do projektu na ikonu. (Vyberte prostředky a v místní nabídce klikněte na tlačítko Přidat a pak na existující položku a vyberte ikonu souboru.)  
  
3.  Otevřete soubor .vsct v editoru.  
  
4.  Přidat `GuidSymbol` element s názvem **testIcon**. Vytvořit identifikátor GUID (**nástroje / vytvořit GUID**, pak vyberte **registru formátu** a klikněte na tlačítko Kopírovat) a vložte ji do `value` atribut. Výsledek by měl vypadat takto:  
  
    ```xml  
    <!-- Create your own GUID -->  
    <GuidSymbol name="testIcon" value="{00000000-0000-0000-0000-0000}">  
    ```  
  
5.  Přidat `<IDSymbol>` ikony. `name` Atribut je na ikonu ID a `value` určuje jeho umístění na pruhu, pokud existuje. Pokud existuje jenom jeden ikonu, přidejte 1. Výsledek by měl vypadat takto:  
  
    ```xml  
    <!-- Create your own GUID -->  
    <GuidSymbol name="testIcon" value="{00000000-0000-0000-0000-0000}">  
        <IDSymbol name="testIcon1" value="1" />  
    </GuidSymbol>  
    ```  
  
6.  Vytvoření `<Bitmap>` v `<Bitmaps>` souboru .vsct představují rastrový obrázek, který obsahuje ikony.  
  
    -   Nastavte `guid` hodnotu na název `<GuidSymbol>` elementu, které jste vytvořili v předchozím kroku.  
  
    -   Nastavte `href` hodnotu na relativní cestu k souboru bitové mapy (v tomto případě **prostředky\\< název souboru ikony\>**.  
  
    -   Nastavte `usedList` hodnotu IDSymbol jste vytvořili dříve. Tento atribut určuje seznam s položkami oddělenými čárkou ikony, které mají být používány VSPackage. Kompilace vyloučené formuláře jsou ikony nejsou na seznamu.  
  
         Rastrový obrázek bloku by měl vypadat takto:  
  
        ```xml  
        <Bitmap guid="testIcon" href="Resources\<icon file name>" usedList="testIcon1"/>  
        ```  
  
7.  Ve stávající `<Button>` , nastavena `Icon` element na GUIDSymbol a IDSymbol hodnoty, které jste vytvořili dříve. Tady je příklad elementu tlačítko s těmito hodnotami:  
  
    ```xml  
    <Button guid="guidAddIconCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">  
        <Parent guid="guidAddIconCmdSet" id="MyMenuGroup" />  
        <Icon guid="testIcon" id="testIcon1" />  
        <Strings>  
            <ButtonText>My Command name</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
8.  Vaše ikona testu. Sestavte projekt a spusťte ladění. V experimentální instance vyhledejte příkaz. Měl by se zobrazit ikonu, že jste přidali.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md)   
 [XML schéma VSCT – referenční informace](../extensibility/vsct-xml-schema-reference.md)