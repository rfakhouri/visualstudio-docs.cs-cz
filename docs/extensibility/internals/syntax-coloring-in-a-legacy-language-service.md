---
title: Barevné zvýrazňování syntaxe ve službě starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- syntax coloring
- language services, syntax coloring
ms.assetid: f65ff67e-8c20-497a-bebf-5e2a5b5b012f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 47d7164df48011907f8bea408c0acf08250d0657
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66331299"
---
# <a name="syntax-coloring-in-a-legacy-language-service"></a>Barevné zvýrazňování syntaxe ve službě starší verze jazyka

Visual Studio používá k identifikaci prvky jazyka a jejich zobrazení pomocí zadaného barev v editoru služby barevné zvýraznění.

## <a name="colorizer-model"></a>Colorizer modelu
 Implementuje služba jazyka <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> rozhraní, které se pak použije v editorech. Tato implementace je samostatný objekt ze služby jazyka, jak je znázorněno na následujícím obrázku:

 ![Obrázek SVC Colorizer](../../extensibility/internals/media/figlgsvccolorizer.gif)

> [!NOTE]
> Služba barevného označování syntaxe je oddělené od obecný mechanismus sady Visual Studio pro barevné zvýrazňování textu. Další informace o Obecné [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] mechanismus podporuje barevné zvýrazňování, naleznete v tématu [pomocí písma a barvy](../../extensibility/using-fonts-and-colors.md).

 Kromě colorizer služba jazyka můžete zadat vlastní které lze zabarvit položky, které jsou používány editorem, reklamy, že poskytuje vlastní, které lze zabarvit položky. Můžete to provést prostřednictvím implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> na stejný objekt, který implementuje rozhraní <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> rozhraní. Vrátí počet položek, které lze zabarvit vlastní, když volá editoru <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> metoda a vrací jednotlivé položky vlastní které lze zabarvit při volání editoru <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> metody.

 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> Metoda vrátí objekt, který implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> rozhraní. Pokud služba jazyka podporuje barevné 24-bit nebo vysoké hodnoty, musí implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> rozhraní na stejný objekt jako <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> rozhraní.

## <a name="how-a-vspackage-uses-a-language-service-colorizer"></a>Jak VSPackage používá Colorizer služby jazyka

1. Sady VSPackage, musíte získat příslušné jazykové služby, který vyžaduje službu jazyka VSPackage provést následující kroky:

    1. Použijte implementaci objektu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> rozhraní se získat text, který má být obarveny.

         Text obvykle bývá zobrazen, použití objektu, který implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> rozhraní.

    2. Získáte službu jazyka pomocí dotazu na poskytovatele služeb balíčku VSPackage pro službu jazyka identifikátor GUID. Jazykové služby jsou označeny v registru příponu souboru.

    3. Přidružit služba jazyka s <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> voláním jeho <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> metoda.

2. Sady VSPackage teď můžete získat a používat objekt colorizer následujícím způsobem:

    > [!NOTE]
    > Rozšíření VSPackages, které používají základní editor není potřeba získat jazyk služby colorizer objekty explicitně. Jakmile instance základní editor získá služby příslušný jazyk, provádět všechny úlohy barevné zvýraznění je vidět tady.

    1. Získání objektu colorizer jazyková služba, která implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>, a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2> rozhraní voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> metoda na službě jazyka <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> objektu.

    2. Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> metoda colorizer informace pro konkrétní rozsah textu.

         <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> Vrátí pole hodnot, jeden pro každý znak v rozsahu textu se barevně zvýrazněné. Hodnoty jsou indexů do seznamu které lze zabarvit položek, které lze zabarvit položky seznamu výchozích udržuje základní editor nebo které lze zabarvit vlastní položky seznamu udržuje samotnou službu jazyka.

    3. Zabarvení informace vrácené <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> metodu pro zobrazení vybraného textu.

> [!NOTE]
> Kromě použití colorizer služby jazyka, VSPackage použít také pro obecné účely mechanismus zbarvení text sady Visual Studio. Další informace o tomto mechanizmu, naleznete v tématu [pomocí písma a barvy](../../extensibility/using-fonts-and-colors.md).

## <a name="in-this-section"></a>V tomto oddílu
- [Implementace barevného zvýrazňování syntaxe](../../extensibility/internals/implementing-syntax-coloring.md)

 Tento článek popisuje, jak editor přistupuje k službě jazyka barevné zvýrazňování syntaxe a služba jazyka musí implementovat pro podporu syntaxe barevné zvýrazňování.

- [Postupy: Použití předdefinovaných položek, které lze zabarvit](../../extensibility/internals/how-to-use-built-in-colorable-items.md)

 Ukazuje, jak používat integrované které lze zabarvit položky ze služby jazyka.

- [Vlastní položky, které lze zabarvit](../../extensibility/internals/custom-colorable-items.md)

 Popisuje, jak implementovat vlastní, které lze zabarvit položky.

## <a name="see-also"></a>Viz také

- [Použití písem a barev](../../extensibility/using-fonts-and-colors.md)