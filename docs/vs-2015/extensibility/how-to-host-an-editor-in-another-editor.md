---
title: 'Postupy: Hostování editoru v jiném editoru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - host a nested editor
ms.assetid: 2b0eb705-fe94-4ca8-93e0-9dbd8ce61a44
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4d4b4ff425feb22b5057a8d1a76b7f73b8932d9f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68204166"
---
# <a name="how-to-host-an-editor-in-another-editor"></a>Postupy: Hostování editoru v jiném editoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V sadě Visual Studio, můžete hostovat jeden editor uvnitř jiného tak, že zadáte jako nadřazené okno hostitelského okna. Uděláte to tak, nastavte parametry <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> a <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> na podřízené okno rámce.  
  
### <a name="to-set-up-the-window-frame-to-host-an-editor"></a>Nastavit okno rámce pro hostování editoru  
  
1. Určení editoru jako hostované editor vytvořením podřízené podokno okna.  
  
     Toto podokno je, kam se obrátit textového editoru.  
  
2. Vytvoření hostujícím editorem pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A> metody.  
  
3. Nastavte <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> a <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> vlastnosti v implementaci rámce okna editoru prostředí tím, že předáte tyto vlastnosti jako parametry <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A> metoda, v uvedeném pořadí.  
  
     Pokud potřebujete načíst tyto parametry, předat vlastnosti tak, aby <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> metody.  
  
4. Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> metody pro editor omezením.  
  
     Editoru se zobrazí v podokně prostředí obsahující editoru.  
  
## <a name="robust-programming"></a>Robustní programování  
 **Návrháře aplikaci** v edici Visual Studio Team pro architekty je příkladem rám okna editoru hostování jiném editoru. **Návrháře aplikaci** hostitelem jiné návrháře v jeho pravého podokna. Panel návrháře (nebo **vlastnosti** stránky) pro každý z obsažených návrháře se přidá do nadřazeného rámu okna.
