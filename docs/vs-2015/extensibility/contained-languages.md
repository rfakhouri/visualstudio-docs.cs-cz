---
title: Jazyky obsažené | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - contained languages
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
caps.latest.revision: 19
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0920999eee7460c8bf697e245bae55a3641b8e18
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184280"
---
# <a name="contained-languages"></a>Obsažené jazyky
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)] 

*Jazyky obsažené* jazyků, které jsou obsaženy v jiných jazycích. Například ve formátu HTML v [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] stránky mohou obsahovat [!INCLUDE[csprcs](../includes/csprcs-md.md)] nebo [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] skripty. Architektura s duální jazyka je vyžadována pro editor souborů .aspx a poskytuje technologie IntelliSense, zabarvení a dalších funkcí pro úpravy pro kód HTML a skriptovací jazyk.  
  
## <a name="implementation"></a>Implementace  
 Nejdůležitější rozhraní je nutné implementovat pro jazyky obsažené <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rozhraní. Toto rozhraní je implementováno v jakémkoliv jazyce, který je možné hostovat ve primárního jazyka. Poskytuje přístup k službě jazyka colorizer filtr zobrazení textu a ID primárního jazyka služby. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory> Vám umožní vytvářet <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rozhraní. Následující kroky ukazují, jak implementovat omezením jazyka:  
  
1. Použití `QueryService()` získat ID služby a interface ID jazyka <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>.  
  
2. Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A> metodu pro vytvoření <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rozhraní. Předávání <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> rozhraní, jeden nebo více [položky ID](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID>) a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> rozhraní.  
  
3. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> Rozhraní, které je objekt koordinátor vyrovnávací paměti textu, poskytuje základní služby, které jsou nutné k mapování umístění v primárním souboru do vyrovnávací paměti pro sekundární jazyk.  
  
     Například v jednom souboru ASPX, obsahuje primární soubor ASP, HTML a veškerý kód, který je obsažen. Sekundární vyrovnávací paměti, ale obsahuje obsažený kód společně s žádné definice tříd, aby sekundární vyrovnávací paměti souboru platný kód. Koordinátora buffer zpracovává práci koordinovat úpravy z vyrovnávací paměti jeden na druhý.  
  
4. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A> Metodu, která je primární jazyk, říká koordinátora buffer, jaký text ve vyrovnávací paměti je namapován na odpovídající text ve vyrovnávací paměti pro sekundární.  
  
     Jazyk předá pole <xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping> strukturou, který aktuálně obsahuje pouze primární a sekundární rozpětí.  
  
5. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A> Metoda a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A> metoda poskytuje mapování z primární na sekundární vyrovnávací paměti a naopak.
