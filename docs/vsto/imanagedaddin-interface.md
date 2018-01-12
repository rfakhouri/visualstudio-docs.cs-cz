---
title: "Imanagedaddin – rozhraní | Microsoft Docs"
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
helpviewer_keywords: IManagedAddin interface
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: ce339bb56368ab5c7e88d1cc8956a3b19a7e89b3
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="imanagedaddin-interface"></a>IManagedAddin – rozhraní
  Implementace imanagedaddin – rozhraní pro vytváření komponenty, která načte spravované doplňků VSTO. Toto rozhraní je přidaná do systému Microsoft Office 2007.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
 Aplikace Microsoft Office, počínaje systém Microsoft Office 2007, použijte imanagedaddin – rozhraní ke spouštění doplňků VSTO pro Office. Imanagedaddin – rozhraní pro vytváření zavaděče vlastní doplňku VSTO můžete implementovat a modul runtime pro spravované doplňků VSTO, místo použití zavaděč doplňku VSTO (VSTOLoader.dll) a [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Další informace najdete v tématu [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
## <a name="how-managed-add-ins-are-loaded"></a>Jak jsou načtena spravované doplňky  
 Při spuštění aplikace dojít k následující kroky:  
  
1.  Aplikace zjistí doplňků VSTO tak, že vyhledá položky v následujícím klíči registru:  
  
     HKEY_CURRENT_USER\Software\Microsoft\Office\\*\<název aplikace >*\Addins\  
  
     Každá položka v tomto klíči registru je jedinečné ID doplňku VSTO. Obvykle je to názvu sestavení doplňku VSTO.  
  
2.  Aplikace vyhledá `Manifest` položka pod položkou pro každý doplňku VSTO.  
  
     Spravované doplňků VSTO můžete uložit úplnou cestu v manifestu `Manifest` položky v rámci HKEY_CURRENT_USER\Software\Microsoft\Office\\*\<název aplikace >*\Addins\\  *\<ID doplněk >*. Manifest je soubor (obvykle soubor XML), který poskytuje informace, které se používají pro načtení doplňku VSTO.  
  
3.  Pokud aplikace vyhledá `Manifest` položku, aplikace se pokusí načíst spravované součásti zavaděč doplňku VSTO. Aplikace k tomu pokusu o vytvoření objektu COM, který implementuje imanagedaddin – rozhraní.  
  
     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Zahrnuje doplňku VSTO zavaděč komponentu (VSTOLoader.dll), nebo můžete vytvořit vlastní pomocí implementace imanagedaddin – rozhraní.  
  
4.  Volání aplikace [IManagedAddin::Load](../vsto/imanagedaddin-load.md) metoda a předává v hodnotě `Manifest` položku.  
  
5.  [IManagedAddin::Load](../vsto/imanagedaddin-load.md) metoda provádí úkoly vyžadované ke spouštění VSTO doplněk, jako je například konfigurace zásad domény a zabezpečení aplikací pro VSTO doplněk, který je právě načítán.  
  
 Další informace o registru klíče, které používají aplikace Microsoft Office ke zjištění a načíst spravované doplňků VSTO najdete v tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
## <a name="guidance-for-implementing-imanagedaddin"></a>Pokyny pro implementaci imanagedaddin –  
 Pokud budete implementovat imanagedaddin –, je nutné zaregistrovat knihovnu DLL, která obsahuje implementaci pomocí následující CLSID:  
  
 99D651D7-5F7C-470E-8A3B-774D5D9536AC  
  
 Aplikace Microsoft Office použít k vytvoření objektu COM, který implementuje imanagedaddin – tento CLSID.  
  
> [!CAUTION]  
>  Tento identifikátor CLSID také používá VSTOLoader.dll v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Proto pokud používáte imanagedaddin – k vytvoření vlastního doplňku VSTO zavaděč a komponenty modulu runtime, nelze nasadit příslušné součásti počítačů se systémem VSTO Add in, které jsou závislé na [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace nespravovaného rozhraní API &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/unmanaged-api-reference-office-development-in-visual-studio.md)  
  
  