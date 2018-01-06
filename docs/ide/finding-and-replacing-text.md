---
title: "Hledání a nahrazení textu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.find
- vs.findreplacecontrol
- vs.findreplace.findsymbol
- vs.findreplace.symbol
- findresultswindow
- vs.findreplace.quickreplace
- vs.findsymbol
- vs.findinfiles
- vs.findresults1
- vs,findsymbolwindow
- vs.findreplace.quickfind
- vs.lookin
- vs.replace
helpviewer_keywords:
- text searches
- Replace in Files dialog box
- find, text
- Find in Files dialog box
- find
- text searches, finding and replacing text
- Replace dialog box
- text, finding and replacing
- find, symbol
- find and replace
- replace
- find text
- replacing text
ms.assetid: a62545c3-1570-4d12-99fb-a82607eb35a1
caps.latest.revision: "31"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 72081f6c140c4634918e67098493cb37bb324848
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="finding-and-replacing-text"></a>Hledání a nahrazení textu
Můžete najít a nahradit text v editoru kódu v sadě Visual Studio a určité textový výstup windows, jako **výsledky hledání** systému windows, pomocí **najít a nahradit** ovládací prvek nebo **najít nebo Nahradit v souborech**. Můžete také hledat a nahradit v některé návrháře windows, například návrháře XAML a návrháři formulářů Windows a nástroj windows  
  
 Můžete určit obor vyhledávání aktuálním dokumentu, aktuální řešení nebo vlastní sadu složek. Můžete také zadat sadu přípon názvů souborů pro hledání několika souborů. Syntaxe vyhledávání lze přizpůsobit pomocí regulárních výrazech .NET.  
  
 Najít a nahradit regulární výrazy, přečtěte si téma [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).  
  
> [!TIP]
>  **Najít/příkaz** pole je stále k dispozici jako ovládacím prvku panel nástrojů, ale nebude ve výchozím nastavení. Můžete zobrazit **najít/příkaz** pole výběrem **přidat nebo odebrat tlačítka** na **standardní** panelu nástrojů a pak vyberete **najít**. Další informace najdete v tématu [pole najít/příkaz](../ide/find-command-box.md).  
  
## <a name="find-and-replace-control"></a>Najít a nahradit ovládací prvek  
 **Najít a nahradit** ovládací prvek se zobrazí v pravém horním rohu okna editoru kódu. **Najít a nahradit** řízení okamžitě označuje všechny výskyty řetězce zadaný hledaný řetězec v aktuálním dokumentu. Můžete přejít z výskytů do jiného tak, že zvolíte **najít další** tlačítko nebo **najít předchozí** tlačítko u ovládacího prvku vyhledávání.  
  
 Možnosti můžete nahrazení kliknutím na tlačítko Další na **najít** textové pole. Chcete-li jeden nahrazení najednou, vyberte **nahradit další** vedle položky **nahradit** textové pole. Pokud chcete nahradit všechny shody, vyberte **nahradit všechny** tlačítko.  
  
 Chcete-li změnit barvu zvýraznění pro shody, vyberte **nástroje** nabídce vyberte možnost **možnosti**a potom zvolte **prostředí**a vyberte **písma a barev** . V **zobrazit nastavení pro** seznamu, vyberte **textového editoru**a potom v **zobrazení položek** seznamu, vyberte **najít zvýrazněte (rozšíření)**.  
  
### <a name="searching-tool-windows"></a>Hledání okna nástrojů  
 Můžete použít **najít** řízení v kódu nebo text systému windows, jako například **výstup** windows, a **Najít výsledky** windows tak, že zvolíte **najít a nahradit**na **upravit** nabídky nebo (CTRL + F).  
  
 Verzi najít ovládací prvek je k dispozici také v některé nástroje systému windows. Například můžete nyní filtrovat seznam ovládacích prvků v **sada nástrojů** okna tak, že zadáte text do vyhledávacího pole. Zahrnout další okna nástrojů, které teď umožňuje hledat jejich obsah **Průzkumníku řešení**, **vlastnosti** okně a **Team Explorer**, mimo jiné.  
  
## <a name="findreplace-in-files"></a>Vyhledání a nahrazení v souborech  
 **Vyhledání a nahrazení v souborech** funguje, jako **najít a nahradit** řídit, s tím rozdílem, že můžete definovat obor pro hledání. Nejenom můžete hledat aktuální soubor otevřete v editoru, ale můžete také prohledat všechny otevřené dokumenty, celé řešení, aktuální projekt a vybrané složky sad. Můžete také prohledat podle přípony názvu souboru. Pro přístup k **vyhledání a nahrazení v souborech** dialogovém okně vyberte **najít a nahradit** na **upravit** nabídky (nebo CTRL + SHIFT + F).  
  
 Pokud vyberete **najít všechny**, **Najít výsledky** se otevře okno a uvádí pro hledání shody. Výběr výsledek v seznamu zobrazí přidružený soubor a klade důraz na shodu. Pokud soubor již není otevřený pro úpravy, je otevřen v karta náhled na pravé straně karty dobře. Můžete použít **najít** řízení k hledání v **Najít výsledky** seznamu.  
  
### <a name="creating-custom-search-folder-sets"></a>Vytváření vlastních vyhledávání složky sad  
 Obor vyhledávání můžete definovat výběrem **zvolte složky výsledků hledání** tlačítko (to vypadá **...** ) vedle položky **Hledat v** pole. V **zvolte složky výsledků hledání** dialogové okno, můžete určit sadu složek, ve kterém se bude vyhledávat a specifikace můžete uložit tak, aby jej můžete znovu použít později. Složky na vzdáleném počítači můžete zadat pouze v případě, že jeho jednotce jsou namapovány na místním počítači.  
  
### <a name="creating-custom-component-sets"></a>Vytváření vlastních součástí sad  
 Součást sady můžete definovat jako obor hledání tak, že zvolíte **upravit sadu součást vlastní** vedle položky **Hledat v** pole. Můžete zadat nainstalované rozhraní .NET nebo COM součásti, projektů sady Visual Studio, které jsou součástí vašeho řešení, nebo jakékoli sestavení nebo typ knihovny (.dll, .tlb, .olb, .exe nebo .ocx). Chcete-li vyhledávat odkazy, vyberte **vypadat v odkazech na** pole.  
  
## <a name="see-also"></a>Viz také  
 [Používání regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md)