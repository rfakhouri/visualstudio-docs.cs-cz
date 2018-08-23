---
title: IDebugBreakpointChecksumRequest2::GetChecksum | Dokumentace Microsoftu
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
- IDebugBreakpointChecksumRequest2::GetChecksum
ms.assetid: ec434882-e5c0-4d76-a58b-22c260d8626e
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b4c3e73a963204076c3e592e4453dc874e4e2cd6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669435"
---
# <a name="idebugbreakpointchecksumrequest2getchecksum"></a>IDebugBreakpointChecksumRequest2::GetChecksum
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugBreakpointChecksumRequest2::GetChecksum](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbreakpointchecksumrequest2-getchecksum).  
  
Načte dokument kontrolního součtu pro zarážku požadavek zadaný jedinečný identifikátor algoritmu kontrolního součtu použít.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetChecksum(   
   REFGUID        guidAlgorithm,  
   CHECKSUM_DATA *pChecksumData  
);  
```  
  
```csharp  
public int GetChecksum(   
   ref Guid               guidAlgorithm,  
   out enum_CHECKSUM_DATA pChecksumData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidAlgorithm`  
 [in] Jedinečný identifikátor algoritmu kontrolního součtu.  
  
 `pChecksumData`  
 [out] Kontrolní součet dokumentu pro požadavek zarážku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje funkci, která kontroluje, zda kontrolní součet dokumentu, který má být vázán, odpovídá jednomu z uživatelského rozhraní.  
  
```cpp#  
bool CDebugProgram::DoChecksumsMatch(CDebugPendingBreakpoint *pPending, CDebugCodeContext *pContext)  
{  
    bool fRet = false;  
    HRESULT hRes;  
  
    // Get the checksum for the document we are about to bind to from the pdb side  
    GUID guidAlgorithmId;  
    BYTE *pChecksum = NULL;  
    ULONG cNumBytes = 0;  
  
    hRes = pContext->GetDocumentChecksumAndAlgorithmId(&guidAlgorithmId, &pChecksum, &cNumBytes);  
  
    if ( S_OK == hRes )  
    {  
        // Get checksum data for the document from the UI (request) side  
        CComPtr<IDebugBreakpointChecksumRequest2> pChecksumRequest;  
  
        hRes = pPending->GetChecksumRequest(&pChecksumRequest);  
  
        if ( S_OK == hRes )  
        {  
            CHECKSUM_DATA data;  
  
            hRes = pChecksumRequest->GetChecksum(guidAlgorithmId, &data);  
  
            if ( S_OK == hRes )  
            {  
                if ( data.ByteCount == cNumBytes && memcmp(data.pBytes, pChecksum, cNumBytes) == 0 )  
                    fRet = true;  
                else  
                    fRet = false;  
  
                // Free up data allocated for checksum data  
                CoTaskMemFree(data.pBytes);  
            }  
            else  
                fRet = true; // checksums not available - user disabed checksums  
        }  
        else  
            fRet = true; // we couldn't get checksum from UI - default to past behavior  
  
        // free up space allocated for checksum from pdb  
        CoTaskMemFree(pChecksum);  
    }  
    else  
        fRet = true; // we don't have a checksum to compare with.  
  
    return ( fRet );  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugBreakpointChecksumRequest2](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2.md)

