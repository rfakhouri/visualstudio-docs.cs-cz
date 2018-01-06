---
title: "Obsažené jazyky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - contained languages
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bfdbc3d1c0e7bbc0b3dc712d9434ca1b49c6feca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="contained-languages"></a>Obsažené jazyky
*Obsažené jazyky* jsou jazyky, které jsou obsaženy v jiných jazycích. Například ve formátu HTML v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] stránky mohou obsahovat [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] nebo [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] skripty. Architektura duální jazyk je vyžadována pro editor souborů .aspx k poskytování technologie IntelliSense, zabarvení a další funkce pro úpravu kódu HTML a skriptovací jazyk.  
  
## <a name="implementation"></a>Implementace  
 Nejdůležitější rozhraní je nutné implementovat pro jazyky obsažené <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rozhraní. Toto rozhraní je implementováno modulem jakýkoli jazyk, který může být hostovaný uvnitř primárního jazyka. Poskytuje přístup ke colorizer služba jazyka, filtr zobrazení textu a ID primární jazyk služby. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory> Umožňuje vytvářet <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rozhraní. Následující kroky vám ukážou, jak implementovat obsažené jazyka:  
  
1.  Použití `QueryService()` získat ID služby a rozhraní ID jazyka <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>.  
  
2.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A> metodu pro vytvoření <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rozhraní. Předat <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> rozhraní, ID položky (jeden nebo více <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_NIL>, <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT>, nebo <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_SELECTION>) a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> rozhraní.  
  
3.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> Rozhraní, což je objekt coordinator textové vyrovnávací paměti, poskytuje základní služby, které jsou nutné k mapování umístění v primárním souboru do vyrovnávací paměti pro sekundární jazyk.  
  
     Například v jednom souboru ASPX, obsahuje primární soubor ASP, HTML a všechny kód, který je obsažen. Sekundární vyrovnávací paměti, ale obsahuje obsažené kód společně s všechny definice tříd, aby sekundární vyrovnávací paměti souboru platný kód. Koordinátor vyrovnávací paměti zpracovává práci při spolupráci úpravy z vyrovnávací paměti jeden na druhý.  
  
4.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A> Metoda, která je primární jazyk, informuje koordinátorem vyrovnávací paměti, jaký text v rámci své vyrovnávací paměti je namapována na odpovídajícího textu ve vyrovnávací paměti pro sekundární.  
  
     Jazyk předá pole <xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping> strukturu, která aktuálně pouze zahrnuje primární a sekundární rozpětí.  
  
5.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A> Metoda a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A> metoda zadat mapování z primární na sekundární vyrovnávací paměti a naopak.