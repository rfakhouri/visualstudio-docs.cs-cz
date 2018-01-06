---
title: "Vyhodnocení místní hodnoty – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], evaluating locals
- expression evaluation, evaluating locals
ms.assetid: 7d1ed528-4e7a-4d8f-87b4-162440644a75
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bad0f751f6f772643f38d4f20b2765affd561fb9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="evaluating-locals"></a>Místní hodnoty – vyhodnocení
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 [GetPropertyInfo –](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) je volána k získání hodnoty místní, a také místní názvu a typu. Vzhledem k tomu, že místní hodnotu závisí na aktuální stav programu, musí být hodnota místní získány z paměti. [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) objekt se používá k vytvoření vazby [IDebugField](../../extensibility/debugger/reference/idebugfield.md) objektu, který představuje místní na požadované místo v paměti, který obsahuje hodnotu. Toto umístění v paměti je reprezentována [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) objektu.  
  
 Tato funkce načítání hodnotu místní je zapouzdřené v podpůrné funkci, který provádí následující úlohy:  
  
1.  Váže `IDebugField` objekt, který chcete paměti získat `IDebugObject` objektu.  
  
2.  Získá hodnotu z paměti. Tato hodnota je reprezentován jako řadu bajtů.  
  
3.  Naformátuje hodnotu na základě typu místní.  
  
4.  Vrátí objekt Obecné, který obsahuje hodnotu místní. V jazyce C#, jedná se `object`, a v jazyce C++ je to `VARIANT`.  
  
## <a name="managed-code"></a>Spravovaný kód  
 Toto je implementace funkce, která načte hodnotu místní ve spravovaném kódu.  
  
```csharp  
namespace EEMC  
{  
    internal class Field  
    {  
        internal static object GetValue(  
            IDebugBinder binder,  
            IDebugField field,  
            Type t,  
            uint size)  
        {  
            if (t == null || size == 0)  return null;  
  
            IDebugObject debugObject = null;  
            binder.Bind(null, field, out debugObject);  
  
            byte[] buffer = new byte[size];  
            for (int i = 0; i < size; i++)  buffer[i] = 0;  
  
            debugObject.GetValue(buffer, size);   
  
            if (t == typeof(sbyte)) return (sbyte) buffer[0];  
            if (t == typeof(short)) return BitConverter.ToInt16(buffer, 0);  
            if (t == typeof(int))   return BitConverter.ToInt32(buffer, 0);  
            if (t == typeof(long))  return BitConverter.ToInt64(buffer, 0);  
            if (t == typeof(byte))  return buffer[0];  
            if (t == typeof(char))  return BitConverter.ToChar(buffer, 0);  
            if (t == typeof(uint))  return BitConverter.ToUInt32(buffer, 0);  
            if (t == typeof(ulong)) return BitConverter.ToUInt64(buffer, 0);  
            if (t == typeof(float)) return BitConverter.ToSingle(buffer, 0);  
            if (t == typeof(double))  return BitConverter.ToDouble(buffer, 0);  
            if (t == typeof(bool))  return BitConverter.ToBoolean(buffer, 0);  
            if (t == typeof(string))  return BitConverter.ToString(buffer, 0);  
            return null;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Nespravovaný kód  
 Toto je implementace funkce, která načte hodnotu místní v nespravovaném kódu. `FieldGetType`se zobrazí v [získávání místní hodnoty](../../extensibility/debugger/getting-local-values.md).  
  
```cpp  
HRESULT FieldGetPrimitiveValue(  
    in  IDebugBinder* pbinder,  
    in  IDebugField*  pfield,  
    out VARIANT*      pvarValue  
    )  
{  
    if (pvarValue == NULL)  
        return E_INVALIDARG;  
    else  
        *pvarValue = 0;  
  
    if (pfield == NULL)  
        return E_INVALIDARG;  
  
    if (pbinder == NULL)  
        return E_INVALIDARG;  
  
    HRESULT hr;  
    UINT          valueSize = 0;  
    BYTE*         pvalueBits = NULL;  
    IDebugObject* pobject    = NULL;  
  
    //get the value as bits  
    hr = pbinder->Bind( NULL, pfield, &pobject );  
    if (FAILED(hr))  
        return hr;  
  
    hr = pobject->GetSize( &valueSize );  
    if (FAILED(hr))  
    {  
        pobject->Release();  
        return hr;  
    }  
  
    pvalueBits = reinterpret_cast<BYTE *>(malloc(valueSize * sizeof(BYTE)));  
    if (!pvalueBits)  
    {  
        pobject->Release();  
        return E_OUTOFMEMORY;  
    }  
  
    hr = pobject->GetValue( pvalueBits, valueSize );  
    pobject->Release();  
    if (FAILED(hr))  
    {  
        free(pvalueBits);  
        return hr;  
    }  
  
    //get the type  
    VARIANT     valueType;  
  
    hr = FieldGetType( pfield, &valueType );  
    if (FAILED(hr))  
    {  
        free(pvalueBits);  
        return hr;  
    }  
  
    //copy a primitive value  
    switch (valueType.vt)  
    {  
    case VT_BSTR:  
        {  
            pvarValue->vt = VT_BSTR;  
            if (valueSize == 0)  
                pvarValue->bstrVal = SysAllocString( OLE("") );  
            else  
                pvarValue->bstrVal =  
                    SysAllocStringByteLen( reinterpret_cast<char*>(pvalueBits),  
                                           valueSize );  
        }  
  
    case VT_BOOL:  
    case VT_I1:  
    case VT_I2:  
    case VT_I4:  
    case VT_I8:  
    case VT_UI1:  
    case VT_UI2:  
    case VT_UI4:  
    case VT_UI8:  
    case VT_R4:  
    case VT_R8:  
        pvarValue->vt = valueType.vt;  
  
        if (valueSize > 8)  
            valueSize = 8;  
        memcpy( &(pvarValue->iVal), pvalueBits, valueSize );  
        break;  
  
    case VT_VOID:  
    case VT_EMPTY:  
        pvarValue->vt = valueType.vt;  
        break;  
  
    default:  
        //not a primitive type  
        VariantClear(&valueType);  
        free(pvalueBits);  
        return E_FAIL;  
    }  
  
    free(pvalueBits);  
    VariantClear(&valueType);  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Ukázka implementace lokální proměnné](../../extensibility/debugger/sample-implementation-of-locals.md)   
 [Získávání místní hodnoty](../../extensibility/debugger/getting-local-values.md)   
 [Kontext vyhodnocení](../../extensibility/debugger/evaluation-context.md)