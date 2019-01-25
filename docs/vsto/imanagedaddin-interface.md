---
title: IManagedAddin – rozhraní
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- IManagedAddin interface
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 03f1623a25f1c0299bc8895eb0c30a390e363791
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54863341"
---
# <a name="imanagedaddin-interface"></a>IManagedAddin – rozhraní
  Implementace imanagedaddin – rozhraní pro vytváření komponenty, která načte spravovaných doplňků VSTO. Toto rozhraní přidal v systému Microsoft Office 2007.  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp
[  
    object,  
    uuid(B9CEAB65-331C-4713-8410-DDDAF8EC191A),  
    pointer_default(unique),  
    oleautomation  
]  
interface IManagedAddin : IUnknown  
{  
    HRESULT Load(  
        [in] BSTR bstrManifestURL,   
        [in] IDispatch *pdispApplication);  
    HRESULT Unload();  
};  
```  
  
## <a name="methods"></a>Metody  
 Následující tabulka shrnuje metody, které jsou definovány imanagedaddin – rozhraní.  
  
|Název|Popis|  
|----------|-----------------|  
|[IManagedAddin::Load](../vsto/imanagedaddin-load.md)|Volá se, když Microsoft Office aplikace načte spravovaného doplňku VSTO.|  
|[IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)|Volá se bezprostředně před Microsoft Office spravovaného doplňku VSTO uvolnění aplikace.|  
  
## <a name="remarks"></a>Poznámky  
 Aplikace Microsoft Office, od verze systému Microsoft Office 2007 pomocí imanagedaddin – rozhraní zavádějí doplňků VSTO pro Office. Můžete implementovat imanagedaddin – rozhraní pro vytváření vlastní zavaděče doplňku VSTO a modul runtime pro spravované doplňků VSTO, namísto použití doplňku VSTO zavaděč (*knihovna VSTOLoader.dll*) a [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Další informace najdete v tématu [doplňků VSTO architektura](../vsto/architecture-of-vsto-add-ins.md).  
  
## <a name="how-managed-add-ins-are-loaded"></a>Jak spravované doplňky jsou načteny.  
 Při spuštění aplikace, dojde k následujícím krokům:  
  
1. Aplikace zjistí doplňků VSTO tím, že hledají záznamy v následujícím klíči registru:  
  
    **HKEY_CURRENT_USER\Software\Microsoft\Office\\*\<název_aplikace >* \Addins\\**  
  
    Každá položka v rámci tohoto klíče registru je jedinečné ID doplňku VSTO. Obvykle je to název sestavení doplňku VSTO.  
  
2. Aplikace vyhledá `Manifest` položky pod položkou pro každý doplňku VSTO.  
  
    Spravované doplňky VSTO můžete ukládat úplnou cestu k manifestu v `Manifest` položku **HKEY_CURRENT_USER\Software\Microsoft\Office\\_\<název_aplikace >_ \Addins\\  _\<ID doplňku >_**. Manifest je soubor (obvykle soubor XML), který poskytuje informace, které slouží k načtení doplňku VSTO.  
  
3. Pokud aplikace zjistí `Manifest` položky, aplikace se pokouší načíst spravované součásti zavaděč doplňku VSTO. Aplikace to provede tak, že zkusíte vytvořit objekt modelu COM, který implementuje imanagedaddin – rozhraní.  
  
    [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Obsahuje součást doplňku VSTO zavaděč (*knihovna VSTOLoader.dll*), nebo můžete vytvořit vlastní implementaci imanagedaddin – rozhraní.  
  
4. Volání aplikace [IManagedAddin::Load](../vsto/imanagedaddin-load.md) metoda a předá v hodnotě `Manifest` položka.  
  
5. [IManagedAddin::Load](../vsto/imanagedaddin-load.md) metoda provede úlohy potřebné pro zavedení doplňku VSTO, jako je například konfigurace zásad aplikací domény a zabezpečení pro VSTO doplněk, který se načítá.  
  
   Další informace o registru spravované klíče, které aplikace Microsoft Office použijte k vyhledání a načtení doplňků VSTO naleznete v tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
## <a name="guidance-to-implement-imanagedaddin"></a>Pokyny k implementaci imanagedaddin –  
 Pokud implementujete imanagedaddin –, budete muset zaregistrovat knihovnu DLL, která obsahuje implementace s použitím následující identifikátor CLSID:  
  
 99D651D7-5F7C-470E-8A3B-774D5D9536AC  
  
 Aplikace Microsoft Office můžete vytvořit objekt modelu COM, který implementuje imanagedaddin – tento identifikátor CLSID.  
  
> [!CAUTION]  
>  Tento identifikátor CLSID také používá *knihovna VSTOLoader.dll* v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Proto pokud používáte imanagedaddin – k vytvoření doplňku VSTO zavaděč a součásti modulu runtime, nemůžete nasadit komponenty do počítačů, na kterých běží doplňků VSTO, které spoléhají na [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
## <a name="see-also"></a>Viz také:  
 [Nespravovaná referenční dokumentace rozhraní API &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/unmanaged-api-reference-office-development-in-visual-studio.md)  
