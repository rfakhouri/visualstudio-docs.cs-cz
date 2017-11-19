---
title: "Postupy: poskytování automatizace pro Windows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], tool windows
- tool windows, automation
ms.assetid: 512ab2a4-7987-4912-8f40-8804bf66f829
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 945eeb8b81ecb26d43da9528db154d133c4f868c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-provide-automation-for-windows"></a>Postupy: poskytování automatizace pro Windows
Můžete zadat automatizace pro dokument a nástroje systému windows. Poskytnete automatizace se doporučuje vždy, když chcete zpřístupnit objekty automatizace v okně prostředí a prostředí již neposkytuje objekt připravených automation, stejně jako se seznamem úkolů.  
  
## <a name="automation-for-tool-windows"></a>Automatizace pro nástroje systému Windows  
 Prostředí poskytuje automatizace na okno nástroje vrácením standardní <xref:EnvDTE.Window> objektu, jak je popsáno v následující postup:  
  
#### <a name="to-provide-automation-for-tool-windows"></a>K poskytování automatizace pro nástroje systému windows  
  
1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> metoda prostřednictvím prostředí s <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> jako `VSFPROPID` parametr získat `Window` objektu.  
  
2.  Pokud požadavky volající objekt automatizace VSPackage specifické pro nástroj okno prostřednictvím <xref:EnvDTE.Window.Object%2A>, volání prostředí `QueryInterface` pro `IExtensibleObject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>, nebo `IDispatch` rozhraní. Obě `IExtensibleObject` a `IVsExtensibleObject` poskytují <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject.GetAutomationObject%2A> metoda.  
  
3.  Když pak zavolá prostředí `GetAutomationObject` metoda předávání `NULL`, reakce předáním zpět VSPackage určitého objektu.  
  
4.  Pokud volání `QueryInterface` pro `IExtensibleObject` a `IVsExtensibleObject` nezdaří, pak zavolá prostředí `QueryInterface` pro `IDispatch`.  
  
## <a name="automation-for-document-windows"></a>Automatizace pro okna dokumentu  
 Standardní <xref:EnvDTE.Document> objektu je také k dispozici z prostředí, i když editor může mít svůj vlastní implementaci `T:EnvDTE.Document` objekt implementací `IExtensibleObject` rozhraní a zpracování `GetAutomationObject`.  
  
 Kromě toho editoru můžete zadat konkrétní VSPackage automatizace objekt, načíst prostřednictvím <xref:EnvDTE.Document.Object%2A> metoda implementací `IVsExtensibleObject` nebo `IExtensibleObject` rozhraní. [VSSDK ukázky](http://aka.ms/vs2015sdksamples) přispívá objekt RTF automatizace specifické pro dokument.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>