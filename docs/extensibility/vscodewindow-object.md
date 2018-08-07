---
title: Vscodewindow – objekt | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b9ef7d4b190a9b2c1a487fb70df33726ca9b3ed4
ms.sourcegitcommit: 56ae5032d99d948aae0548ae318ca2bae97ea962
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/07/2018
ms.locfileid: "39586271"
---
# <a name="vscodewindow-object"></a>Vscodewindow – objekt
Okno kódu je okno specializované dokumentu, který může obsahovat jedno nebo více zobrazení textu, obvykle <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objektu.  
  
 Okno kódu je architektonicky, okno dokumentu, který je v rámci okna. Okno kódu je funkčně, jednoduše okno dokumentu rozšířených o další funkce. V režimu rozhraní více dokumentů (MDI) okno kódu je podřízený rámec MDI. Další informace najdete v tématu [přizpůsobení kódu windows pomocí starší verze rozhraní API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md).  
  
 Následující tabulka obsahuje rozhraní v <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|Poskytuje mechanismus obecný přístup k vyhledání služby, který identifikuje globálně jedinečný identifikátor (GUID).|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|Představuje více podřízených dokumentu (MDI interface) obsahující jeden nebo více zobrazení kódu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Vyplní celé okno rámce.|  
  
## <a name="see-also"></a>Viz také:  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [Úpravy obrázků](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)