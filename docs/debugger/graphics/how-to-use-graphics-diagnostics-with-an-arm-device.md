---
title: "Postupy: použití diagnostiky grafiky s zařízení s ARM | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 346fd3c0-9e92-4ab8-bb3b-1aa9000a2483
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 60898b7ea37c7e732453fd03f9c557b2494f66c5
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="how-to-use-graphics-diagnostics-with-an-arm-device"></a>Postupy: použití diagnostiky grafiky s zařízení s ARM
Diagnostika grafiky podporuje vzdálené ladění aplikací Direct3D – na bázi ARM zařízení se systémem Windows RT 8.1 nebo Windows Phone 8.1. Můžete zaznamenání grafických informací z aplikace Direct3D – při spuštění v zařízení, nebo použít zařízení jako počítač přehrávání dříve zaznamenaný grafických informací.  
  
## <a name="using-graphics-diagnostics-with-an-arm-based-device"></a>Použití diagnostiky grafiky ARM zařízení se systémem  
 Vzhledem k sadě Visual Studio nepodporuje běží na bázi ARM zařízení, budete muset použít k analýze aplikaci, která běží na nich vzdáleného ladicího programu. Vzdáleného ladicího programu podporuje grafiky záznam a přehrávání, aby mohli diagnostikovat chyby vykreslování a vyhodnotit grafický výkon v těchto zařízeních stejným způsobem jako můžete ladění aplikace s nimi.  
  
 Pokud chcete používat funkce diagnostiky grafiky, nejprve povolte, vzdálené ladění na vašem zařízení.  
  
#### <a name="to-enable-remote-debugging-on-your-arm-based-device"></a>K povolení vzdáleného ladění na bázi ARM zařízení  
  
1.  Nainstalujte [ARM sadách zásad](http://msdn.microsoft.com/windows/desktop/dn469188) na bázi ARM zařízení.  
  
2.  Nainstalujte [vzdáleného ladění nástrojů](http://go.microsoft.com/fwlink/?LinkId=393086) na bázi ARM zařízení.  
  
> [!IMPORTANT]
>  Pro zařízení Windows Phone 8.1 možná budete muset registraci telefonu pro vývoj. Uděláte to tak, musí být registrovaný developer. Další informace najdete v tématu [postup nasazení a spuštění aplikace pro Windows Phone 8](http://msdn.microsoft.com/library/windowsphone/develop/ff402565.aspx).  
  
 Po povolení vzdáleného ladění na zařízení, ujistěte se, je váš cíl ladění a spuštění diagnostiky grafiky.  
  
#### <a name="to-configure-and-start-graphics-diagnostics-on-your-device"></a>Ke konfiguraci a spuštění diagnostiky grafiky ve vašem zařízení  
  
1.  Na **platformy řešení** rozevíracího seznamu vyberte **ARM** tak, aby zařízení založené na ARM nebude k dispozici jako vzdáleného ladění cíl.  
  
2.  Na **cíl ladění** rozevíracího seznamu vyberte zařízení ARM.  
  
3.  V nabídce zvolte **ladění**, **grafiky**, **spustit diagnostické nástroje**. (Klávesové: Alt + F5)  
  
## <a name="see-also"></a>Viz také  
 [Spuštění aplikace UWP ve vzdáleném počítači](../run-windows-store-apps-on-a-remote-machine.md)   
 [Postupy: Změna počítače pro přehrávání diagnostiky grafiky](how-to-change-the-graphics-diagnostics-playback-machine.md)