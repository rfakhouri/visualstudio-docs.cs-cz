---
title: Objekt VSCodeWindow | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2de0998a3d89c1af3e18fa60aa3f8511716f6165
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="vscodewindow-object"></a>Objekt VSCodeWindow
Okno kódu je okna specializované dokumentu, který může obsahovat jedno nebo více zobrazení textu, obvykle <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objektu.  
  
 V okně kód je z pohledu architektury okna dokumentu, který je v rámci okna. V okně kód je funkčně, jednoduše okna dokumentu s další funkce. V režimu rozhraní více dokumentů (MDI) je v okně Kód rámečku podřízeného MDI. Další informace najdete v tématu [přizpůsobení Windows kódu pomocí starší verze rozhraní API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md).  
  
 Následující tabulka obsahuje rozhraní v <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|Poskytuje mechanismus obecný přístup najít službu, která identifikuje globálně jedinečný identifikátor (GUID).|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|Představuje několika podřízenými rozhraní (MDI) dokument obsahující jeden nebo více zobrazení kódu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Doplní rámce okna.|  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [Úprava obrázků](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)