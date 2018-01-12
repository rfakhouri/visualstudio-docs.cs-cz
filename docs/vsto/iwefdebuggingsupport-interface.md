---
title: "Iwefdebuggingsupport – rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 7b132c51e12d553bcd6e722e87c8aeee96be5e5c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="iwefdebuggingsupport-interface"></a>IWefDebuggingSupport – rozhraní
  Implementované ladění prostředí, jako je například Visual Studio, aby se usnadnilo ladění aplikací pro Office. Aplikace Office, jako je například Word či Excel, získá toto rozhraní ze sady Visual Studio a potom volá metody rozhraní v určitých bodech během ladicí relace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[  
    uuid(ccaf1a90-ce1c-4199-9cd6-b40c5c57a671),  
    oleautomation  
]  
interface IWefDebuggingSupport : IUnknown  
{  
    HRESULT SetWefProcessId(  
        [in] DWORD dwProcessId);  
    HRESULT GetAutoInsertExtensions(  
        [out, retval] SAFEARRAY(BSTR)* psaExtensionNames);  
}  
```  
  
## <a name="methods"></a>Metody  
 V následující tabulce jsou uvedené metody, které definuje iwefdebuggingsupport – rozhraní.  
  
|Název|Popis|  
|----------|-----------------|  
|[GetAutoInsertExtensions – metoda](../vsto/getautoinsertextensions-method.md)|Získá informace o aplikacích pro Office, které se mají automaticky vložit během ladění.|  
|[SetWefProcessId – metoda](../vsto/setwefprocessid-method.md)|Poskytuje identifikátor procesu, který se spustí Web rozšíření Framework (WEF) obsah.|  
  
  