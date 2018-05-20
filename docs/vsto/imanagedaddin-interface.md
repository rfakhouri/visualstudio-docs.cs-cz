---
title: IManagedAddin – rozhraní
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- IManagedAddin interface
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f29356a3e11634d742d6f6022c35cf8f10871eec
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="imanagedaddin-interface"></a>IManagedAddin – rozhraní
  Implementace imanagedaddin – rozhraní pro vytváření komponenty, která načte spravované doplňků VSTO. Toto rozhraní je přidaná do systému Microsoft Office 2007.  
  
## <a name="syntax"></a>Syntaxe  
  
```c++
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
 V následující tabulce jsou uvedené metody, které jsou definovány imanagedaddin – rozhraní.  
  
|Název|Popis|  
|----------|-----------------|  
|[IManagedAddin::Load](../vsto/imanagedaddin-load.md)|Volá se, když aplikace Microsoft Office aplikace načte spravované Add-in VSTO.|  
|[IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)|Volá se bezprostředně před Microsoft Office spravované Add-in VSTO uvolnění aplikace.|  
  
## <a name="remarks"></a>Poznámky  
 Aplikace Microsoft Office, počínaje systém Microsoft Office 2007, použijte imanagedaddin – rozhraní ke spouštění doplňků VSTO pro Office. Imanagedaddin – rozhraní pro vytváření zavaděče vlastní doplňku VSTO můžete implementovat a modul runtime pro spravované doplňků VSTO, místo použití doplňku VSTO zavaděč (*VSTOLoader.dll*) a [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Další informace najdete v tématu [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
## <a name="how-managed-add-ins-are-loaded"></a>Jak jsou načtena spravované doplňky  
 Při spuštění aplikace dojít k následující kroky:  
  
1.  Aplikace zjistí doplňků VSTO tak, že vyhledá položky v následujícím klíči registru:  
  
     **HKEY_CURRENT_USER\Software\Microsoft\Office\\_\<název aplikace >_ \Addins\**  
  
     Každá položka v tomto klíči registru je jedinečné ID doplňku VSTO. Obvykle je to názvu sestavení doplňku VSTO.  
  
2.  Aplikace vyhledá `Manifest` položka pod položkou pro každý doplňku VSTO.  
  
     Spravované doplňků VSTO můžete uložit úplnou cestu v manifestu `Manifest` položky v rámci **HKEY_CURRENT_USER\Software\Microsoft\Office\\_\<název aplikace >_ \Addins\\  _\<ID doplněk >_**. Manifest je soubor (obvykle soubor XML), který poskytuje informace, které se používají pro načtení doplňku VSTO.  
  
3.  Pokud aplikace vyhledá `Manifest` položku, aplikace se pokusí načíst spravované součásti zavaděč doplňku VSTO. Aplikace k tomu pokusu o vytvoření objektu COM, který implementuje imanagedaddin – rozhraní.  
  
     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Zahrnuje zavaděč komponentu doplňku VSTO (*VSTOLoader.dll*), nebo můžete vytvořit vlastní pomocí implementace imanagedaddin – rozhraní.  
  
4.  Volání aplikace [IManagedAddin::Load](../vsto/imanagedaddin-load.md) metoda a předává v hodnotě `Manifest` položku.  
  
5.  [IManagedAddin::Load](../vsto/imanagedaddin-load.md) metoda provádí úkoly vyžadované ke spouštění VSTO doplněk, jako je například konfigurace zásad domény a zabezpečení aplikací pro VSTO doplněk, který je právě načítán.  
  
 Další informace o registru klíče, které používají aplikace Microsoft Office ke zjištění a načíst spravované doplňků VSTO najdete v tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
## <a name="guidance-to-implement-imanagedaddin"></a>Pokyny k implementaci imanagedaddin –  
 Pokud budete implementovat imanagedaddin –, je nutné zaregistrovat knihovnu DLL, která obsahuje implementaci pomocí následující CLSID:  
  
 99D651D7-5F7C-470E-8A3B-774D5D9536AC  
  
 Aplikace Microsoft Office použít k vytvoření objektu COM, který implementuje imanagedaddin – tento CLSID.  
  
> [!CAUTION]  
>  Tento identifikátor CLSID také používá *VSTOLoader.dll* v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Proto pokud používáte imanagedaddin – k vytvoření vlastního doplňku VSTO zavaděč a komponenty modulu runtime, nelze nasadit příslušné součásti počítačů se systémem VSTO Add in, které jsou závislé na [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
## <a name="see-also"></a>Viz také  
 [Nespravovaná referenční dokumentace rozhraní API &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/unmanaged-api-reference-office-development-in-visual-studio.md)  
  
  