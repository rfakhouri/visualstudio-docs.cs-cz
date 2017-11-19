---
title: "Idiastackframe – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackFrame interface
ms.assetid: 486d25b8-a590-41c1-bdb5-faff3ae35632
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30b3ca5d68731fccf874b250741a6e67697539fb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackframe"></a>IDiaStackFrame
Zpřístupní vlastnosti rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaStackFrame : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Metody tímto rozhraním podporován jsou následující:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaStackFrame::get_allocatesBasePointer](../../debugger/debug-interface-access/idiastackframe-get-allocatesbasepointer.md)|Získá příznak označující, že základní ukazatel je přidělen pro kód v tomto rozsahu adres. Tato metoda je zastaralá.|  
|[Idiastackframe::get_base –](../../debugger/debug-interface-access/idiastackframe-get-base.md)|Získá základní adresu rámečku.|  
|[Idiastackframe::get_cplusplusexceptionhandling –](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)|Získá příznak označující, že zpracovávání výjimek v jazyce C++ je v platnosti.|  
|[IDiaStackFrame::get_functionStart](../../debugger/debug-interface-access/idiastackframe-get-functionstart.md)|Získá příznak označující, zda blok obsahuje vstupní bod funkce.|  
|[Idiastackframe::get_lengthlocals –](../../debugger/debug-interface-access/idiastackframe-get-lengthlocals.md)|Získá počet bajtů lokální proměnné nabídnutých v zásobníku.|  
|[Idiastackframe::get_lengthparams –](../../debugger/debug-interface-access/idiastackframe-get-lengthparams.md)|Získá počet bajtů parametrů nabídnutých v zásobníku.|  
|[Idiastackframe::get_lengthprolog –](../../debugger/debug-interface-access/idiastackframe-get-lengthprolog.md)|Získá počet bajtů kódu prologu v bloku|  
|[Idiastackframe::get_lengthsavedregisters –](../../debugger/debug-interface-access/idiastackframe-get-lengthsavedregisters.md)|Získá počet bajtů uložené registry nabídnutých v zásobníku.|  
|[Idiastackframe::get_localsbase –](../../debugger/debug-interface-access/idiastackframe-get-localsbase.md)|Získá základní adresu lokální proměnné.|  
|[Idiastackframe::get_maxstack –](../../debugger/debug-interface-access/idiastackframe-get-maxstack.md)|Načte maximální počet bajtů nabídnutých v zásobníku v rámečku.|  
|[Idiastackframe::get_rawlvarinstancevalue –](../../debugger/debug-interface-access/idiastackframe-get-rawlvarinstancevalue.md)|Načte hodnotu zadaného místní proměnné nezpracovaná bajtů.|  
|[Idiastackframe::get_registervalue –](../../debugger/debug-interface-access/idiastackframe-get-registervalue.md)|Načte hodnotu zadaného registrace.|  
|[Idiastackframe::get_returnaddress –](../../debugger/debug-interface-access/idiastackframe-get-returnaddress.md)|Načte zpětná adresa rámečku.|  
|[Idiastackframe::get_size –](../../debugger/debug-interface-access/idiastackframe-get-size.md)|Získá velikost rámce v bajtech.|  
|[IDiaStackFrame::get_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md)|Získá příznak označující, že systém výjimek je v platnosti.|  
|[Idiastackframe::get_type –](../../debugger/debug-interface-access/idiastackframe-get-type.md)|Načte typ rámce.|  
  
## <a name="remarks"></a>Poznámky  
 Rámec zásobníku je abstrakcí volání funkce během jejího provádění.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat voláním toto rozhraní [idiaenumstackframes::Next –](../../debugger/debug-interface-access/idiaenumstackframes-next.md) metoda. Najdete v článku [idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md) rozhraní pro příklad týkající se získání `IDiaStackFrame` rozhraní.  
  
## <a name="example"></a>Příklad  
 Tento příklad zobrazuje různé atributy rámce zásobníku.  
  
```C++  
void PrintStackFrame(IDiaStackFrame* pFrame)  
{  
    if (pFrame != NULL)  
    {  
        ULONGLONG bottom = 0;  
        ULONGLONG top    = 0;  
  
        if (pFrame->get_base(&bottom) == S_OK &&  
            pFrame->get_registerValue( CV_REG_ESP, &top ) == S_OK )  
        {  
             printf("range = 0x%08I64x - 0x%08I64x\n", bottom, top);  
        }  
  
        ULONGLONG returnAddress = 0;  
        if (pFrame->get_returnAddress(&returnAddress) == S_OK)  
        {  
             printf("return address = 0x%08I64x\n", returnAddress);  
        }  
  
        DWORD lengthFrame     = 0;  
        DWORD lengthLocals    = 0;  
        DWORD lengthParams    = 0;  
        DWORD lengthProlog    = 0;  
        DWORD lengthSavedRegs = 0;  
        if (pFrame->get_size(&lengthFrame) == S_OK &&  
            pFrame->get_lengthLocals(&lengthLocals) == S_OK &&  
            pFrame->get_lengthParams(&lengthParams) == S_OK &&  
            pFrame->get_lengthProlog(&lengthProlog) == S_OK &&  
            pFrame->get_lengthSavedRegisters(&lengthSavedRegs) == S_OK)  
        {  
            printf("stack frame size          = 0x%08lx bytes\n", lengthFrame);  
            printf("length of locals          = 0x%08lx bytes\n", lengthLocals);  
            printf("length of parameters      = 0x%08lx bytes\n", lengthParams);  
            printf("length of prolog          = 0x%08lx bytes\n", lengthProlog);  
            printf("length of saved registers = 0x%08lx bytes\n", lengthSavedRegs);  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [Idiaenumstackframes::Next –](../../debugger/debug-interface-access/idiaenumstackframes-next.md)   
 [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md)