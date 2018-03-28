---
title: Obsažené jazyky | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - contained languages
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7ec180689f4dadfb60832259ddee51a05f336fda
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="contained-languages"></a>Obsažené jazyky

*Obsažené jazyky* jsou jazyky, které jsou obsaženy v jiných jazycích. Například ve formátu HTML v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] stránky mohou obsahovat [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] nebo [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] skripty. Architektura duální jazyk je vyžadována pro editor souborů .aspx k poskytování technologie IntelliSense, zabarvení a další funkce pro úpravu kódu HTML a skriptovací jazyk.

## <a name="implementation"></a>Implementace

Nejdůležitější rozhraní je nutné implementovat pro jazyky obsažené <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rozhraní. Toto rozhraní je implementováno modulem jakýkoli jazyk, který může být hostovaný uvnitř primárního jazyka. Poskytuje přístup ke colorizer služba jazyka, filtr zobrazení textu a ID primární jazyk služby. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory> Umožňuje vytvářet <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rozhraní. Následující kroky vám ukážou, jak implementovat obsažené jazyka:

1.  Použití `QueryService()` získat ID služby a rozhraní ID jazyka <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>.

2.  Chcete-li vytvořit <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rozhraní, volejte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A> metoda. Předat <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> rozhraní, jeden nebo více [položky ID](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID>)a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> rozhraní.

3.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> Rozhraní, což je objekt coordinator textové vyrovnávací paměti, poskytuje základní služby, které jsou nutné k mapování umístění v primárním souboru do vyrovnávací paměti pro sekundární jazyk.

     Například v jednom souboru ASPX, obsahuje primární soubor ASP, HTML a všechny kód, který je obsažen. Sekundární vyrovnávací paměť však obsahuje pouze obsažené kód společně s všechny definice tříd, aby sekundární vyrovnávací paměti souboru platný kód. Koordinátor vyrovnávací paměti zpracovává práci při spolupráci úpravy z vyrovnávací paměti jeden na druhý.

4.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A> Metoda, která je primární jazyk, informuje koordinátorem vyrovnávací paměti, jaký text v rámci své vyrovnávací paměti je namapována na odpovídajícího textu ve vyrovnávací paměti pro sekundární.

     Jazyk předá pole <xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping> strukturu, která aktuálně pouze zahrnuje primární a sekundární rozpětí.

5.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A> Metoda a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A> metoda zadat mapování z primární na sekundární vyrovnávací paměti a naopak.