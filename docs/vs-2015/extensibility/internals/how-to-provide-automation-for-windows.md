---
title: 'Postupy: poskytování automatizace pro Windows | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], tool windows
- tool windows, automation
ms.assetid: 512ab2a4-7987-4912-8f40-8804bf66f829
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f6fad49e2841186cea677a165bdb48c4a1af5b41
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675423"
---
# <a name="how-to-provide-automation-for-windows"></a>Postupy: poskytování automatizace pro Windows
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [jak: poskytuje automatizaci pro Windows](https://docs.microsoft.com/visualstudio/extensibility/internals/how-to-provide-automation-for-windows).  
  
Můžete zadat automatizace pro dokumentů a nástrojů systému windows. Poskytování automatizace se doporučuje pokaždé, když chcete zpřístupnit objekty automatizace v okně a prostředí už neposkytuje předem připravená automatizační objekt, stejně jako se seznamem úkolů.  
  
## <a name="automation-for-tool-windows"></a>Automatizace pro nástroj Windows  
 Prostředí poskytuje automatizaci na panelu nástrojů tak, že vrací standardní <xref:EnvDTE.Window> objektu, jak je popsáno v následujícím postupu:  
  
#### <a name="to-provide-automation-for-tool-windows"></a>K poskytování automatizace pro nástroje systému windows  
  
1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> metodu prostřednictvím prostředí s <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> jako `VSFPROPID` parametr zobrazíte `Window` objektu.  
  
2.  Pokud volající požaduje objekt automatizace VSPackage specifické pro okno nástroje prostřednictvím <xref:EnvDTE.Window.Object%2A>, volání prostředí `QueryInterface` pro `IExtensibleObject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>, nebo `IDispatch` rozhraní. Obě `IExtensibleObject` a `IVsExtensibleObject` poskytují <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject.GetAutomationObject%2A> metoda.  
  
3.  Když pak volá prostředí `GetAutomationObject` metody předáním `NULL`, odpověď předáním zpět VSPackage konkrétní objekt.  
  
4.  Pokud volání `QueryInterface` pro `IExtensibleObject` a `IVsExtensibleObject` nezdaří, pak prostředí volá `QueryInterface` pro `IDispatch`.  
  
## <a name="automation-for-document-windows"></a>Automatizace pro Windows dokumentu  
 Standardní <xref:EnvDTE.Document> objektu je také k dispozici z prostředí, i když editor může mít svůj vlastní implementaci `T:EnvDTE.Document` objekt implementací `IExtensibleObject` rozhraní a reakce na `GetAutomationObject`.  
  
 Kromě toho editoru můžete zadat konkrétní VSPackage automatizační objekt, načíst prostřednictvím <xref:EnvDTE.Document.Object%2A> metoda implementací `IVsExtensibleObject` nebo `IExtensibleObject` rozhraní. [VSSDK ukázky](../../misc/vssdk-samples.md) přispívá objekt automatizace specifické pro dokument ve formátu RTF.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>

