---
title: Zobrazení definice typů v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/10/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code editor, view definition
- go to definition
- peek definition
- type definition [Visual Studio]
- member definition [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 61428294fc9c4afa32a50b4776f03ce1e98b83b9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="view-type-and-member-definitions"></a>Definice zobrazení typu a členu

Vývojáři často potřebují zobrazit zdrojový kód definice pro typy nebo členy třídy, které používají v svůj kód. V sadě Visual Studio **přejít k definici** a **funkce Náhled definice** funkce umožňují snadno zobrazit definici typ nebo člen. Pokud zdrojový kód není k dispozici, zobrazí se místo toho metadat.

## <a name="go-to-definition"></a>Přechod na definici

**Přejít k definici** funkce přejde na zdroj typ nebo člen a výsledek otevře novou záložku. Pokud se uživatel klávesnice, umístěte ukazatel myši na text někde v názvu symbolu a stiskněte klávesu **F12**. Pokud používáte myši, vyberte buď **přejít k definici** z místní nabídky nebo pomocí **Ctrl + kliknutí** funkcí popsaných v následující části.

### <a name="ctrl-click-go-to-definition"></a>CTRL + kliknutí přechod na definici

V aplikaci Visual Studio 2017 verzi 15.4, je pro uživatele, myš snadný způsob, jak rychle přístup **přejít k definici**. Po stisknutí klávesy se můžete kliknout symboly **Ctrl** při přechodu myší nad typ nebo člen. Chcete-li rychle přejít k definici symbol, stiskněte **Ctrl** klíče a potom klikněte na jeho. Je to snadné!

![Myši kliknutím na Přejít do definice animace](../ide/media/click_gotodef.gif)

Můžete změnit modifikační klávesy pro kliknutí myší **přejít k definici** přechodem na **nástroje** > **možnosti** > **textového editoru**   >  **Obecné**a vyberte buď **Alt** nebo **Ctrl + Alt** z **použití modifikační klávesy**rozevíracího seznamu. Můžete také zakázat kliknutí myší **přejít k definici** zrušením zaškrtnutí políčka **povolit myši klikněte na provést přejít k definici** zaškrtávací políčko.

![Povolení kliknutí myší přechod na definici](../ide/media/editor_options_mouse_click_gotodef.png)

## <a name="peek-definition"></a>Funkce Náhled definice

**Funkce Náhled definice** funkce umožňuje zobrazit náhled definici typu, aniž byste museli opustit vaše aktuální umístění v editoru. Pokud se uživatel klávesnice, umístěte ukazatel myši na text někde uvnitř typ nebo člen název a stiskněte klávesu **Alt + F12**. Pokud používáte myši, můžete si vybrat **funkce Náhled definice** v místní nabídce. V aplikaci Visual Studio 2017 verze 15,4 a novější je nový způsob zobrazení funkce Náhled definice pomocí myši. První, přejděte na **nástroje** > **možnosti** > **textového editoru** > **Obecné**. Vyberte možnost **otevřít v zobrazení funkce Náhled definice** a klikněte na tlačítko **OK** zavřete **možnosti** dialogové okno.

![Nastavení možnosti kliknutí myší funkce Náhled definice](../ide/media/editor_options_peek_view.png)

Potom stiskněte klávesu **Ctrl** (nebo libovolného modifikační klávesy je vybraný v **možnosti**) a klikněte na typ nebo člen.

![Funkce Náhled definice animace](../ide/media/peek_definition.gif)

Pokud jste prohlížet jinou definici z automaticky otevíraném okně, začněte s popisem cesty cesta, která můžete přejít pomocí kružnice a šipek, které se zobrazují nad automaticky otevřeném okně.

Další informace najdete v tématu [postupy: zobrazení a úpravy kódu s použitím funkce Náhled definice (Alt + F12)](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md).

## <a name="view-metadata-as-source-code-c"></a>Zobrazení metadat jako zdrojový kód (C#)

Při zobrazení definice typů jazyka C# nebo členy, jejichž zdrojový kód není k dispozici, zobrazí se místo toho jejich metadat. Můžete zobrazit prohlášení o typy a členy, ale není jejich implementace.

Při spuštění **přejít k definici** nebo **funkce Náhled definice** příkazu pro položku jejichž zdrojový kód je k dispozici, záložkách dokument, který obsahuje zobrazení, že položka metadat, zobrazí jako zdrojový kód Zobrazí se v editoru kódu. Název typu následovaný **[z metadat]**, se zobrazí na kartě dokumentu.

Například pokud spustíte **přejít k definici** příkazu pro <xref:System.Console>, metadata pro <xref:System.Console> se zobrazí v editoru kódu jako zdrojový kód C#. Kód podobá jeho deklaraci, ale nezobrazuje implementace.

![Metadata jako zdroj](../ide/media/metadatasource.png "MetadataSource")

> [!NOTE]
> Při pokusu o spuštění **přejít k definici** nebo **funkce Náhled definice** příkaz pro typy nebo členy, které jsou označené jako interní sady Visual Studio nezobrazuje jako zdrojový kód, bez ohledu na to, jestli jejich metadat odkazující sestavení je přítele či nikoli.

### <a name="view-decompiled-source-definitions-instead-of-metadata-c"></a>Zobrazit definice decompiled zdrojů místo metadata (C#)

Nové ve Visual Studio 2017 verze 15,6 operací, můžete nastavit možnost při zobrazení definice jazyka C# typ nebo člen, jejichž zdrojový kód je k dispozici, najdete v části decompiled zdrojového kódu. Chcete-li tuto funkci zapnout, vyberte **nástroje** > **možnosti** z řádku nabídek. Potom rozbalte **textového editoru** > **C#** > **Upřesnit**a vyberte **přepínat na decompiled zdroje**.

![Zobrazení decompiled definice](media/go-to-definition-decompiled-sources.png)

> [!NOTE]
> Visual Studio rekonstruuje pomocí ILSpy dekompilace těla metody. Při prvním používat tuto funkci, musí přijmout právní omezení týkající se softwaru licencování a autorských právech a ochranné zákony.

## <a name="see-also"></a>Viz také

[Navigace v kódu](../ide/navigating-code.md)

[Postupy: zobrazení a úpravy kódu s použitím funkce Náhled definice (Alt + F12)](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)
