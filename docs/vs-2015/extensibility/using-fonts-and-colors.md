---
title: Použití písem a barev | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fonts, controlling in IDE
- IDE, controlling text color and fonts
- Fonts and Colors property page
- font and color control [Visual Studio SDK]
- text, IDE
ms.assetid: d1a9b99f-fbdc-45ed-920a-e08c3d931ac9
caps.latest.revision: 28
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6db4f030a3367a5fd2fb449b3515643fe6cd6033
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628251"
---
# <a name="using-fonts-and-colors"></a>Použití písem a barev
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [pomocí písma a barvy](https://docs.microsoft.com/visualstudio/extensibility/using-fonts-and-colors).  
  
[!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] Poskytuje podporu pro použití písem a barev k zobrazení textu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Písma a barvy – přehled](../extensibility/font-and-color-overview.md)  
 Tento článek popisuje nastavení písem a barev textu v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] integrované vývojové prostředí (IDE). Také seznámíte se základními pojmy kategorií a zobrazit položky a popisuje, jak pomocí rozšíření VSPackages a základní editor atributů textu.  
  
 [Písma a barvy informace pro barevné zvýraznění textu](../extensibility/getting-font-and-color-information-for-text-colorization.md)  
 Poskytuje pokyny pro implementaci zabarvení textu v balíčcích VSPackage, která spravovat **kategorie** jiné než **textový Editor**.  
  
 [Přístup k uložené písma a barev](../extensibility/accessing-stored-font-and-color-settings.md)  
 Vysvětluje, jak aktuální písmo a barvu nastavení lze ukládat, načíst a použít.  
  
 [Implementace vlastní kategorie a zobrazit položky](../extensibility/implementing-custom-categories-and-display-items.md)  
 Popisuje základní kroky, podle kterých můžete vytvářet a používat svůj vlastní z okna **zobrazit položky** a **kategorie** pro podporu zobrazení textu.  
  
 Tento přístup vyžaduje VSPackage k implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> rozhraní a související rozhraní.  
  
 [Postupy: přístup k vestavěné písma a barvy schéma](../extensibility/how-to-access-the-built-in-fonts-and-color-scheme.md)  
 Popisuje, jak definovat a registrovat kategorie pomocí integrované písmo a barvy a zahájení používání nástroje poskytované systémem písma a barvy.  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>  
 Poskytuje instance `IVsFontAndColorDefaults` nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> rozhraní, které odpovídá určité položky uvedené v **zobrazit nastavení pro** v seznamu **písma a barvy** stránky **Možnosti** dialogové okno.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>  
 Umožňuje VSPackage pro podporu rozhraní IDE **písma a barvy** stránky tak, že definujete výchozí písma a barvy pro okno nebo komponenty uživatelského rozhraní.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup>  
 Poskytuje mechanismus, pomocí kterého VSPackage, která poskytuje podporu písma a barvy můžete určit skupinu položek zobrazení – přístupem zahrnujícím nadřazené kategorie, která představuje sjednocení dvou nebo více kategorií.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>  
 Umožňuje načíst data písma a barvy, nebo uložit do registru VSPackage.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents>  
 Upozorní rozšíření VSPackages, který používáte v nastavení písem a barev písma a barvy informace o změnách.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorUtilities>  
 Poskytuje nástroje pro práci s vstupní a výstupní data, která používá metody [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] **písma a barvy** mechanismus.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager>  
 Ovládací prvky, ukládání do mezipaměti nastavení písem a barev.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vývoj služby starší verze jazyka](../extensibility/internals/developing-a-legacy-language-service.md)  
 Popisuje, jak balíčky VSPackages použití jazykových služeb k přizpůsobení [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] editoru.  
  
 [Barevné zvýrazňování syntaxe ve vlastních editorech](../extensibility/syntax-coloring-in-custom-editors.md)  
 Descries jak [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] editor používá jazykové služby k implementaci barevné zvýrazňování syntaxe.  
  
 [Rozšíření dalších částí sady Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)  
 Vysvětluje způsob používání [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] služeb vytvořil prvky uživatelského rozhraní, které odpovídají zbytek [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].

