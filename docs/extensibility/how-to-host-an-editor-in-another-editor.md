---
title: 'Postupy: Hostování editoru v jiném editoru | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - host a nested editor
ms.assetid: 2b0eb705-fe94-4ca8-93e0-9dbd8ce61a44
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5dffffd8f2857dbb048b829cec0d2e7847a05c5f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021137"
---
# <a name="how-to-host-an-editor-in-another-editor"></a>Postupy: Hostitel editoru v jiném editoru

V sadě Visual Studio můžete hostovat jeden editor uvnitř jiného tak, že zadáte jako nadřazené okno hostitelského okna. Uděláte to tak, nastavte parametry <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2.VSFPROPID_ParentHwnd> a <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2.VSFPROPID_ParentFrame> na podřízené okno rámce.

## <a name="to-set-up-the-window-frame-to-host-an-editor"></a>Nastavit okno rámce pro hostování editoru

1.  Určení editoru jako hostované editor vytvořením podřízené podokno okna.

     Toto podokno je, kam se obrátit textového editoru.

2.  Vytvoření hostujícím editorem pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A> metody.

3.  Nastavte <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2.VSFPROPID_ParentHwnd> a <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2.VSFPROPID_ParentFrame> vlastnosti v implementaci rámce okna editoru prostředí tím, že předáte tyto vlastnosti jako parametry <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A> metoda, v uvedeném pořadí.

     Pokud potřebujete načíst tyto parametry, předat vlastnosti tak, aby <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> metody.

4.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> metody pro editor omezením.

     Editoru se zobrazí v podokně prostředí obsahující editoru.

## <a name="robust-programming"></a>Robustní programování

**Návrháře aplikaci** v edici Visual Studio Team pro architekty je příkladem rám okna editoru hostování jiném editoru. **Návrháře aplikaci** hostitelem jiné návrháře v jeho pravého podokna. Panel návrháře (nebo **vlastnosti** stránky) pro každý z obsažených návrháře se přidá do nadřazeného rámu okna.