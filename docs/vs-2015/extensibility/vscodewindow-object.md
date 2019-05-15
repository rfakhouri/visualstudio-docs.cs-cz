---
title: Vscodewindow – objekt | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 511c730ec3a11b02d46f5e9c9271c028bb4fa325
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65690776"
---
# <a name="vscodewindow-object"></a>VSCodeWindow – objekt
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Okno kódu je okno specializované dokumentu, který může obsahovat jedno nebo více zobrazení textu, obvykle <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objektu.  
  
 Okno kódu je architektonicky, okno dokumentu, který je v rámci okna. Okno kódu je funkčně, jednoduše okno dokumentu rozšířených o další funkce. V režimu rozhraní více dokumentů (MDI) okno kódu je podřízený rámec MDI. Další informace najdete v tématu [přizpůsobení kódu Windows s použitím rozhraní API starší verze](../extensibility/customizing-code-windows-by-using-the-legacy-api.md).  
  
 Následující tabulka obsahuje rozhraní v <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|Poskytuje mechanismus obecný přístup k vyhledání služby, který identifikuje globálně jedinečný identifikátor (GUID).|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|Představuje více podřízených dokumentu (MDI interface) obsahující jeden nebo více zobrazení kódu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Vyplní celé okno rámce.|  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [Úpravy obrázků](https://msdn.microsoft.com/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)
