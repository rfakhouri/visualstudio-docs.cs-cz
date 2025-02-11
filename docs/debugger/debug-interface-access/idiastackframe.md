---
title: Idiastackframe – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame interface
ms.assetid: 486d25b8-a590-41c1-bdb5-faff3ae35632
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3252d15ebfb06fa840bfad6bf74dc3b8748776ef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838090"
---
# <a name="idiastackframe"></a>IDiaStackFrame
Zpřístupní vlastnosti rámec zásobníku.

## <a name="syntax"></a>Syntaxe

```
IDiaStackFrame : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
Dál jsou uvedené metody tímto rozhraním podporován:

|Metoda|Popis|
|------------|-----------------|
|[IDiaStackFrame::get_allocatesBasePointer](../../debugger/debug-interface-access/idiastackframe-get-allocatesbasepointer.md)|Získá příznak označující, že je základní ukazatel přidělen pro kód v tomto rozsahu adres. Tato metoda je zastaralá.|
|[IDiaStackFrame::get_base](../../debugger/debug-interface-access/idiastackframe-get-base.md)|Získá základní adresu rámce.|
|[IDiaStackFrame::get_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)|Získá příznak označující, že zpracování výjimek jazyka C++ je v platnosti.|
|[IDiaStackFrame::get_functionStart](../../debugger/debug-interface-access/idiastackframe-get-functionstart.md)|Získá příznak označující, že blok obsahuje vstupního bodu funkce.|
|[IDiaStackFrame::get_lengthLocals](../../debugger/debug-interface-access/idiastackframe-get-lengthlocals.md)|Získá počet bajtů lokálních proměnných posunuto v zásobníku.|
|[IDiaStackFrame::get_lengthParams](../../debugger/debug-interface-access/idiastackframe-get-lengthparams.md)|Získá počet bajtů z parametrů předaných v zásobníku.|
|[IDiaStackFrame::get_lengthProlog](../../debugger/debug-interface-access/idiastackframe-get-lengthprolog.md)|Získá počet bajtů prologu kód v bloku|
|[IDiaStackFrame::get_lengthSavedRegisters](../../debugger/debug-interface-access/idiastackframe-get-lengthsavedregisters.md)|Získá počet bajtů uložených registrů posunuto v zásobníku.|
|[IDiaStackFrame::get_localsBase](../../debugger/debug-interface-access/idiastackframe-get-localsbase.md)|Získá základní adresu místních hodnot.|
|[IDiaStackFrame::get_maxStack](../../debugger/debug-interface-access/idiastackframe-get-maxstack.md)|Získá maximální počet bajtů posunuto v zásobníku v rámci.|
|[IDiaStackFrame::get_rawLVarInstanceValue](../../debugger/debug-interface-access/idiastackframe-get-rawlvarinstancevalue.md)|Načte hodnotu místní proměnné zadané jako nezpracovaný bajtů.|
|[IDiaStackFrame::get_registerValue](../../debugger/debug-interface-access/idiastackframe-get-registervalue.md)|Načte hodnotu zadaného registru.|
|[IDiaStackFrame::get_returnAddress](../../debugger/debug-interface-access/idiastackframe-get-returnaddress.md)|Získá zpáteční adresu rámce.|
|[IDiaStackFrame::get_size](../../debugger/debug-interface-access/idiastackframe-get-size.md)|Získá velikost rámce v bajtech.|
|[IDiaStackFrame::get_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md)|Získá příznak označující, že zpracování výjimek systému je v platnosti.|
|[IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)|Načte typ rámce.|

## <a name="remarks"></a>Poznámky
Rámec zásobníku je abstrakcí během jejího provádění volání funkce.

## <a name="notes-for-callers"></a>Poznámky pro volající
Získat voláním toto rozhraní [idiaenumstackframes::Next –](../../debugger/debug-interface-access/idiaenumstackframes-next.md) metody. Najdete v článku [idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md) rozhraní příklad týkající se získání `IDiaStackFrame` rozhraní.

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

DLL: msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)
- [IDiaEnumStackFrames::Next](../../debugger/debug-interface-access/idiaenumstackframes-next.md)
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)
