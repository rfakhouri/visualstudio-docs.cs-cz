---
title: IPropertyProxyEESide::GetManagedViewerCreationData | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
helpviewer_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
ms.assetid: c4eb4d60-8816-4d52-bc8d-dffd4f066499
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b5161894875ac683e5a6e49ae623bd6025531006
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199531"
---
# <a name="ipropertyproxyeesidegetmanagedviewercreationdata"></a>IPropertyProxyEESide::GetManagedViewerCreationData
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Aby bylo možné vytvořit instanci tohoto prohlížeče načte informace o prohlížeči pro tento typ vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetManagedViewerCreationData(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  className,  
   ASSEMBLYLOCRESOLUTION* alr,  
   BOOL*                  replacementOk  
);  
```  
  
```csharp  
int GetManagedViewerCreationData(  
   out string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     className,  
   out enum_ASSEMBLYLOCRESOLUTION alr,  
   out int                        replacementOk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `assemName`  
 [out] Vrátí název sestavení, která uchovává tento objekt.  
  
 `assemBytes`  
 [out] Vrátí [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objekt, který obsahuje počet bajtů sestavení tohoto objektu (to je hodnota null, pokud nejsou k dispozici žádné bajtů).  
  
 `assemPdb`  
 [out] Vrátí `IEEDataStorage` objekt, který obsahuje symbol ukládání informací pro tento objekt (to je hodnota null, pokud je k dispozici žádné úložiště symbolů).  
  
 `className`  
 [out] Vrací název třídy obsahující tento objekt.  
  
 `alr`  
 [out] Vrátí hodnotu z [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) výčet označující umístění sestavení.  
  
 `replacementOk`  
 [out] Vrátí nenulovou hodnotu (`TRUE`) Pokud je hodnota tohoto objektu můžete změnit; nula (`FALSE`) je-li objekt je jen pro čtení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda používá k vytvoření instance spravovaný prohlížeč vizualizérů typů.  
  
## <a name="see-also"></a>Viz také  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
