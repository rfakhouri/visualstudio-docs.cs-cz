---
title: IDebugProcess2::GetAttachedSessionName | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 39975163cdddf06ba87add52e60c9a81581985ab
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54781800"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá název relace, která je ladění tohoto procesu. Integrované vývojové prostředí můžete zobrazit tyto informace pro uživatele, který se ladí konkrétní proces na daném počítači.  
  
> [!NOTE]
>  Tato metoda je zastaralá a jeho implementace by měla vždy vrátit `E_NOTIMPL`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrSessionName`  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda by měla vždy vrátit `E_NOTIMPL`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
