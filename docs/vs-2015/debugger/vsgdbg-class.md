---
title: Třída VsgDbg | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6722263c-ccef-40c7-a0ae-87a863fbab00
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 053647d48324f056148375bae9268b997ba8721f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68145697"
---
# <a name="vsgdbg-class"></a>VsgDbg – třída
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Reprezentuje rozhraní pro programovací řízení součásti diagnostiky grafiky v aplikaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
class VsgDbg;  
```  
  
## <a name="members"></a>Členové  
 `VsgDbg` Třída podporuje následující členy.  
  
### <a name="public-constructors"></a>Veřejné konstruktory  
  
|Name|Popis|  
|----------|-----------------|  
|[VsgDbg::VsgDbg (konstruktor)](../debugger/vsgdbg-vsgdbg-constructor.md)|Vytvoří instanci objektu `VsgDbg` třídy a volitelně připraví komponentu v aplikaci diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací.|  
|[VsgDbg::~VsgDbg (destruktor)](../debugger/vsgdbg-tilde-vsgdbg-destructor.md)|Odstraní instanci `VsgDbg` třídy.|  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Name|Popis|  
|----------|-----------------|  
|[AddMessage](../debugger/addmessage.md)|Přidá vlastní zprávu pro diagnostiku grafiky HUD (zobrazení vedoucí nahoru).|  
|[BeginCapture](../debugger/begincapture.md)|Začne sběr intervalu, který bude končit `EndCapture`.|  
|[CaptureCurrentFrame](../debugger/capturecurrentframe.md)|Zaznamená zbytek aktuálního snímku do souboru protokolu grafiky.|  
|[Copy (zachytávání prostřednictvím kódu programu)](../debugger/copy-programmatic-capture.md)|Zkopíruje obsah aktivní grafiky (.vsglog) protokolu do nového souboru.|  
|[EndCapture](../debugger/endcapture.md)|Končí zachycení interval, který byl spuštěn s `BeginCapture`.|  
|[Init](../debugger/init.md)|Připraví komponentu v aplikaci diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací.|  
|[ToggleHUD](../debugger/togglehud.md)|Přepíná překrytí HUD diagnostiky grafiky, nebo vypnout.|  
|[UnInit](../debugger/uninit.md)|Soubor protokolu grafiky dokončí, zavře a uvolní prostředky, které byly použity při aplikaci se aktivně zaznamenávání informací grafiky.|  
  
## <a name="remarks"></a>Poznámky  
 `VsgDbg` Třída představuje rozhraní, které můžete použít k ovládání funkcí diagnostiky grafiky prostřednictvím kódu programu. Některé funkce můžete použít i v případě, že nejsou aktivně zachytávání a zaznamenávání informací grafiky; Jedná se o `AddMessage` členské funkce a `ToggleHUD` členskou funkci. Členské funkce Příprava součást diagnostiky grafiky, spuštění nebo zastavení aktivní zachycení informací grafiky v aplikaci, nebo musí být volána, zatímco tato aplikace je aktivně zachytávání a zaznamenání grafických informací do souboru protokolu grafiky.
