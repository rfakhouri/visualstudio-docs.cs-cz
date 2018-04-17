---
title: VsgDbg – třída | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 6722263c-ccef-40c7-a0ae-87a863fbab00
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a37c2313b35091b5f939526f58b73effde285fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vsgdbg-class"></a>VsgDbg – třída
Představuje rozhraní pro programové řízení komponenty v aplikaci diagnostiky grafiky sady.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
class VsgDbg;  
```  
  
## <a name="members"></a>Členové  
 `VsgDbg` Třída podporuje následující členy.  
  
### <a name="public-constructors"></a>Veřejné konstruktory  
  
|Název|Popis|  
|----------|-----------------|  
|[VsgDbg::VsgDbg (konstruktor)](vsgdbg-vsgdbg-constructor.md)|Vytvoří instanci objektu `VsgDbg` třídy a volitelně připraví v aplikaci součást diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací.|  
|[VsgDbg::~VsgDbg (destruktor)](vsgdbg-tilde-vsgdbg-destructor.md)|Odstraní instanci `VsgDbg` třídy.|  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Název|Popis|  
|----------|-----------------|  
|[AddMessage](addmessage.md)|Přidá vlastní zprávu do diagnostiky grafiky HUD (zobrazení Head-Up).|  
|[BeginCapture](begincapture.md)|Zahájí zachycení interval, který bude končit `EndCapture`.|  
|[CaptureCurrentFrame](capturecurrentframe.md)|Zaznamená zbytek aktuální rámec grafiky souboru protokolu.|  
|[Copy (zachytávání prostřednictvím kódu programu)](copy-programmatic-capture.md)|Zkopíruje obsah souboru protokolu (.vsglog) active grafiky do nového souboru.|  
|[EndCapture](endcapture.md)|Ukončí zachycení interval, který byl spuštěn s `BeginCapture`.|  
|[Init](init.md)|Připraví v aplikaci součást diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací.|  
|[ToggleHUD](togglehud.md)|Přepne do překrytí HUD diagnostiky grafiky zapnout nebo vypnout.|  
|[UnInit](uninit.md)|Dokončí soubor protokolu grafiky, zavře se a uvolní prostředky, které jste použili při aplikaci se aktivně zaznamenání grafických informací.|  
  
## <a name="remarks"></a>Poznámky  
 `VsgDbg` Třída představuje rozhraní, které můžete použít k ovládání funkcí diagnostiky grafiky prostřednictvím kódu programu. Některé funkce, můžete použít i v případě, že není aktivně zaznamenání a zaznamenání grafických informací; To zahrnuje `AddMessage` – členská funkce a `ToggleHUD` – členská funkce. Členské funkce buď připravit v aplikaci součást diagnostiky grafiky spuštění nebo zastavení active zaznamenání grafických informací, nebo musí být volána, když je aktivně zaznamenávání a zaznamenání grafických informací do souboru protokolu grafiky aplikace.