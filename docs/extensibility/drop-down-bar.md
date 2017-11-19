---
title: "Rozevírací seznam panelu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - drop-down bar
ms.assetid: 4bb621bd-72f5-43d5-916f-9f66617da049
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2f5da476bb9b54b536cb296112d578574822e410
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="drop-down-bar"></a>Panel rozevíracího seznamu
Panelu rozevíracího seznamu je k dispozici v horní části okna kódu a obsahuje dva rozevírací seznamy.  
  
## <a name="drop-down-bar-interfaces"></a>Rozhraní panelu rozevíracího seznamu  
 V [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], například panelu rozevírací seznam obsahuje seznamy pro [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] položky a [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] položky členské funkce, jak je znázorněno na následujícím obrázku.  
  
 ![Vyřaďte & č. 45; dolů řádky](../extensibility/media/vsdropdown_bar.gif "vsDropdown_bar")  
Panel rozevíracího seznamu  
  
 Při implementaci panelu rozevíracího seznamu, existují čtyři rozhraní pro primární význam:  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarClient>  
  
     Implementace tohoto rozhraní k vložení obsahu panelu rozevíracího seznamu. Každé kombinaci rozevírací seznam může obsahovat prostý text nebo zvláštní text (tučné, podtržení nebo kurzíva), může mít barevné zvýrazňování písmo textu okno nebo šedě písma zvýrazňování a volitelně můžete zadat malý rastrový obrázek vedle rozevíracího seznamu položky. Podobně jako <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> rozhraní, rastrové obrázky jsou k dispozici v seznamech obrázků. Každé kombinaci rozevíracího seznamu může mít jinou bitovou kopii seznamu; Každý seznamu obrázků však musí obsahovat bitové kopie stejné výšky. Kromě toho používání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarClient.GetComboTipText%2A> metodu, můžete zadat popisek pro každou kombinaci.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager>  
  
     Volání toto rozhraní k vytvoření nebo zrušení panelu rozevírací seznam pro údržbu kódu. Toto rozhraní lze také použít k určení, zda rozevíracího seznamu panelu je již připojen k okno kódu voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.GetDropdownBar%2A> metoda. Volání <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> pro <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager> z <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBar>  
  
     Volání toto rozhraní komunikovat přímo s panelu rozevíracího seznamu. Toto rozhraní můžete vynutit aktualizaci z rozevírací nabídky panelu obsah nebo chcete-li změnit výběr v jednom ze seznamu polí.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents>  
  
     Pokud jste zaregistrovali `ShowDropdownBarOption` v klíči registru služby váš jazyk pak okno správce svého kódu třeba sledovat tuto událost, chcete-li synchronizovat s preference uživatele o tom, jestli se má zobrazit na panelu rozevíracího seznamu. Pokud v klíč služby jazyk nezaregistrujete tuto možnost, pak je zakázána možnost zobrazení nebo skrytí panelu rozevíracího seznamu na **možnosti** nabídky.  
  
## <a name="attaching-a-drop-down-bar-to-a-code-window"></a>Rozevírací seznam panelu se připojuje k kódu – okno  
 K připojení rozevíracího seznamu řádku do okna kódu, když je vytvořeno, by měla služba jazyka přiřadit z rozevírací nabídky panelu, když <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A> metoda je volána. Pokud volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.GetDropdownBar%2A> metoda určuje, že rozevírací seznam panelu již neexistuje, poté volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.AddDropdownBar%2A>. Pro přístup k <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager> rozhraní, volejte <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> z <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> ukazatel vrácena pro vás, pokud vaše <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> implementace byla připojena.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení Windows kódu pomocí starší verze rozhraní API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)   
 [Podpora pro navigační panel ve službě jazyk starší verze](../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)