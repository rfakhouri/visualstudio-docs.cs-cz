---
title: "Text značky pomocí starší verze rozhraní API | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - text markers
ms.assetid: 937a0b19-1216-45d5-a7ad-4fe1d6f73097
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 98c889bc1bc128a941f726348781a633799475de
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-text-markers-with-the-legacy-api"></a>Text značky pomocí starší verze rozhraní API
Text značky je plovoucí rozsah textu ve vyrovnávací paměť, která může mít vliv na zobrazení a chování oblasti textu. Značky zahrnují zarážky, záložky, podtržení vlnovkami a oblasti jen pro čtení. Text značky jsou v podstatě liší od barevné zvýrazňování syntaxe. Barevné zvýrazňování syntaxe je rychlý způsob, jak sdělit syntaxe jazyka, který je přidružené k oblasti textu. Barevné zvýrazňování syntaxe je obecně požadovány při Windows překreslí obrazovky, když je důležité rychlost. Barevné zvýrazňování syntaxe změní barvu textu. Text značek můžete změnit mnoho dalších vlastností text. Text značek můžete "float" a použít zvláštní chování barevné zvýrazňování.  
  
 Z důvodu nároky na výkon související se text značkami nevytvářejte mnoho značek pro vaše textové vyrovnávací paměti. Každé značky se aktualizuje vždy, že uživatel upravuje obsah vyrovnávací paměti.  
  
> [!NOTE]
>  Uživatelé mohou změnit barvu typ viditelné značky, ale ne jeho tvar a styl. Další informace najdete v tématu [písma a barvy, prostředí, dialogové okno Možnosti](../ide/reference/fonts-and-colors-environment-options-dialog-box.md).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Postupy: Přidání značek standardního textu](../extensibility/how-to-add-standard-text-markers.md)|Popisuje postup přidání značka typu standardního textového poskytované [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní editoru textového zobrazení.|  
|[Postupy: implementace chyba značky](../extensibility/how-to-implement-error-markers.md)|Popisuje, jak implementovat instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] značky, který slouží k označení chyb pomocí červené podtržení vlnovkou.|  
|[Postupy: vytvoření vlastní Text značek](../extensibility/how-to-create-custom-text-markers.md)|Popisuje postup vytvoření a přidání značka typu vlastní text do textového zobrazení.|  
|[Postupy: použití značek textu](../extensibility/how-to-use-text-markers.md)|Vysvětluje postup přidání značek text.|  
|[V editoru jádra](../extensibility/inside-the-core-editor.md)|Popisuje funkce editoru jádra a poskytuje podrobné informace o tom, jak přizpůsobit editor jádra.|  
|[Funkce editoru](http://msdn.microsoft.com/en-us/bdac940d-1f14-4019-a01f-fd0bb3dc7198)|Popisuje funkce dostupné v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní editor.|  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType>  
 Poskytuje mechanismus uniform k získání informací o typu značky určitý text, ať už předdefinovaná v nástroji editor nebo registrovaných VSPackage.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLineMarker>  
 Poskytuje přístup k a nastaví pozice značku text v textové vyrovnávací paměti pomocí dvourozměrná souřadnice.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker>  
 Poskytuje metody pro správu text značek.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient>  
 Poskytuje zpětná volání a [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE a další procesy, které se používají k úpravě textu značku.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced>  
 Rozšiřuje funkce, která je k dispozici prostřednictvím <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní tím, že poskytuje další zpětných volání.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>  
 Rozšiřuje funkce, která je k dispozici prostřednictvím <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní tím, že poskytuje další zpětných volání.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerColorSet>  
 Umožňuje typ značky k určení, zda jiné typy značky sdílet stejnou sadu barev.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider>  
 Poskytuje kontext pro označení textu v editoru jádra. Pro každý typ značky text, který je v editoru jádra, rozhraní IDE vytvoří samostatné <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> objektu.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerGlyphDropHandler>  
 Obslužná rutina, která je k dispozici pro značky, jejichž glyfů podpora přetažení myší. Glyf je ikonu, která určuje pozici značku.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider>  
 Vrátí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType> rozhraní služba, která poskytuje značek k jiné VSPackages text.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStreamMarker>  
 Poskytuje přístup k a nastaví pozice značku text v textové vyrovnávací paměti pomocí jednorozměrné souřadnice. Pokud je možné, nepoužívejte toto rozhraní.