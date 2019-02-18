---
title: 'Postupy: Poskytování automatizace pro Windows | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], tool windows
- tool windows, automation
ms.assetid: 512ab2a4-7987-4912-8f40-8804bf66f829
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4a4482069d16ef6f0f64472b838057949890a6d3
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335152"
---
# <a name="how-to-provide-automation-for-windows"></a>Postupy: Poskytování automatizace pro windows

Můžete zadat automatizace pro dokumentů a nástrojů systému windows. Poskytování automatizace se doporučuje pokaždé, když chcete zpřístupnit objekty automatizace v okně a prostředí už neposkytuje předem připravená automatizační objekt, stejně jako se seznamem úkolů.

## <a name="automation-for-tool-windows"></a>Automatizace pro nástroje systému windows

Prostředí poskytuje automatizaci na panelu nástrojů tak, že vrací standardní <xref:EnvDTE.Window> objektu, jak je popsáno v následujícím postupu:

1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> metodu prostřednictvím prostředí s [__VSFPROPID. VSFPROPID_ExtWindowObject](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_ExtWindowObject>) jako `VSFPROPID` parametr zobrazíte `Window` objektu.

2.  Pokud volající požaduje objekt automatizace VSPackage specifické pro okno nástroje prostřednictvím <xref:EnvDTE.Window.Object%2A>, volání prostředí `QueryInterface` pro `IExtensibleObject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>, nebo `IDispatch` rozhraní. Obě `IExtensibleObject` a `IVsExtensibleObject` poskytují <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject.GetAutomationObject%2A> metoda.

3.  Když pak volá prostředí `GetAutomationObject` metody předáním `NULL`, odpověď předáním zpět VSPackage konkrétní objekt.

4.  Pokud volání `QueryInterface` pro `IExtensibleObject` a `IVsExtensibleObject` nezdaří, pak prostředí volá `QueryInterface` pro `IDispatch`.

## <a name="automation-for-document-windows"></a>Automatizace pro okna dokumentu

Standardní <xref:EnvDTE.Document> objektu je také k dispozici z prostředí, i když editor může mít svůj vlastní implementaci <xref:EnvDTE.Document> objekt implementací `IExtensibleObject` rozhraní a reakce na `GetAutomationObject`.

Kromě toho editoru můžete zadat konkrétní VSPackage automatizační objekt, načíst prostřednictvím <xref:EnvDTE.Document.Object%2A> metoda implementací `IVsExtensibleObject` nebo `IExtensibleObject` rozhraní. [VSSDK ukázky](http://aka.ms/vs2015sdksamples) přispívá objekt automatizace specifické pro dokument ve formátu RTF.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>