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
ms.assetid: 0bd1c6a6-67a5-4478-b942-8b937b28f723
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 150c8794fb35ca017be7e0873dc0d1b84ebfc38c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
  