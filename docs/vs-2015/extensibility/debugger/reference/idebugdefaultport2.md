---
title: IDebugDefaultPort2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugDefaultPort2
helpviewer_keywords:
- IDebugDefaultPort2 interface
ms.assetid: 7b3452af-9a96-4c4c-9946-4339b72d3d7b
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 135578a0047466f7f284ede28f5b161cfe04d57b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49205455"
---
# <a name="idebugdefaultport2"></a>IDebugDefaultPort2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní poskytuje několik metod pro přístup k serveru portu a oznámení zařízení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDefaultPort2 : IDebugPort2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio implementuje toto rozhraní k reprezentaci ladění pro přístup k programy. Dodavatel port. Tento vlastní port můžete také implementovat toto rozhraní, pokud zpracovává vzdálené ladění.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Argument metody [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) rozhraní poskytuje toto rozhraní. Volání [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) na [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) rozhraní můžete získat také toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod definovaných v [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md), toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)|Získá rozhraní portu oznámení z tohoto portu.|  
|[GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)|Získá rozhraní na serveru, který hostuje tento port.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugdefaultport2-queryislocal.md)|Určuje, zda tento port je spuštěna na místním počítači.|  
  
## <a name="remarks"></a>Poznámky  
 Název "`IDebugDefaultPort2`" je hodně misnomer, protože nepředstavuje výchozí port. Může mít název "IDebugPort3."  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)

