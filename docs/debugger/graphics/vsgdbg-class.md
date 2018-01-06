---
title: "VsgDbg – třída | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6722263c-ccef-40c7-a0ae-87a863fbab00
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e1a3810f6f0c2de6bffb2f97c2f1fc446ea3b6d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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