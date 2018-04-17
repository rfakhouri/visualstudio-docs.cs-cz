---
title: 'Návod: Zaznamenání grafických informací prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 899c5e233a8afb898d7864d388448a186b8ab781
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-capturing-graphics-information-programmatically"></a>Návod: Zaznamenání grafických informací prostřednictvím kódu
Můžete použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] diagnostiky grafiky k prostřednictvím kódu programu zaznamenání grafických informací z aplikace Direct3D.  
  
 Zachytávání prostřednictvím kódu programu je užitečný ve scénářích, jako například:  
  
-   Začněte zachytávání prostřednictvím kódu programu, až aplikace grafiky nepoužívá swapchain existuje, například když vykresluje texturou.  
  
-   Začněte zachytávání prostřednictvím kódu programu, až aplikace nemá vykreslení vůbec, například když používá DirectCompute k provádění výpočtů.  
  
-   Volání `CaptureCurrentFrame`při vykreslování problém je obtížné předvídat a zaznamenat v manuálním testováním, ale můžete pomocí informací o stavu aplikace za běhu prostřednictvím kódu programu předpovědět.  
  
##  <a name="CaptureDX11_2"></a> Zachytávání prostřednictvím kódu programu v systému Windows 10  
 Tato část průvodce ukazuje zachytávání prostřednictvím kódu programu v aplikacích, které používají rozhraní API 11.2 DirectX ve Windows 10, která používá metodu robustní zachycení.
  
 V této části ukazuje, jak provést tyto úlohy:  
  
-   Příprava aplikace použít zachytávání prostřednictvím kódu programu  
  
-   Získání rozhraní IDXGraphicsAnalysis  
  
-   Zachycení informací grafiky  
  
> [!NOTE]
>  Předchozích implementacích zachytávání prostřednictvím kódu programu spolehlivé vzdálených nástrojů pro Visual Studio pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nakonfigurovánu zachycení.
  
### <a name="preparing-your-app-to-use-programmatic-capture"></a>Příprava aplikace použít zachytávání prostřednictvím kódu programu  
 Pokud chcete použít zachytávání prostřednictvím kódu programu ve vaší aplikaci, musí obsahovat potřebné hlavičky. Tyto hlavičky jsou součástí Windows 10 SDK.  
  
##### <a name="to-include-programmatic-capture-headers"></a>Chcete-li patří hlavičky zachytávání prostřednictvím kódu programu  
  
-   Zdrojový soubor, ve které definujete rozhraní IDXGraphicsAnalysis zahrňte tyto hlavičky:  
  
    ```  
    #include <DXGItype.h>  
    #include <dxgi1_2.h>  
    #include <dxgi1_3.h>  
    #include <DXProgrammableCapture.h>  
    ```  
  
    > [!IMPORTANT]
    >  Nezahrnovat záhlaví souboru vsgcapture.h—which podporuje zachytávání prostřednictvím kódu programu na Windows 8.0 a starší – provádět v vaší aplikace pro Windows 10 zachytávání prostřednictvím kódu programu. Tuto hlavičku není kompatibilní s DirectX 11.2. Pokud tento soubor je zahrnuto po zahrnuté hlavičku d3d11_2.h, vydá upozornění. Pokud vsgcapture.h je zahrnutý před d3d11_2.h, aplikace se nespustí.  
  
    > [!NOTE]
    >  Pokud 2010 června DirectX SDK je v počítači nainstalován a obsahuje cesta zahrnutí vašeho projektu `%DXSDK_DIR%includex86`, ho přesunout na konec cesty zahrnutí. Totéž pro vaši cestu knihovny.  
  
### <a name="getting-the-idxgraphicsanalysis-interface"></a>Získání rozhraní IDXGraphicsAnalysis  
 Než budete moct zachytit grafických informací z DirectX 11.2, budete muset získat rozhraní DXGI ladění.  
  
> [!IMPORTANT]
>  Pokud používáte zachytávání prostřednictvím kódu programu, musí stále spuštění aplikace v rámci diagnostiky grafiky (Alt + F5 v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]) nebo v části [nástroje příkazového řádku snímek](command-line-capture-tool.md).  
  
##### <a name="to-get-the-idxgraphicsanalysis-interface"></a>Chcete-li získat rozhraní IDXGraphicsAnalysis  
  
-   Použijte následující kód spojit rozhraní IDXGraphicsAnalysis rozhraní DXGI ladění.  
  
    ```  
    IDXGraphicsAnalysis* pGraphicsAnalysis;  
    HRESULT getAnalysis = DXGIGetDebugInterface1(0, __uuidof(pGraphicsAnalysis), reinterpret_cast<void**>(&pGraphicsAnalysis));  
    ```  
  
     Nezapomeňte se podívat `HRESULT` vrácený [DXGIGetDebugInterface1](https://msdn.microsoft.com/library/windows/desktop/dn457937(v=vs.85).aspx) zajistit získat platný rozhraní dříve, než ho použijete:  
  
    ```  
    if (FAILED(getAnalysis))  
    {  
        // Abort program or disable programmatic capture in your app.  
    }  
    ```  
  
    > [!NOTE]
    >  Pokud `DXGIGetDebugInterface1` vrátí `E_NOINTERFACE` (`error: E_NOINTERFACE No such interface supported`), zajistěte, aby aplikace běží v rámci diagnostiky grafiky (Alt + F5 v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]).  
  
### <a name="capturing-graphics-information"></a>Zachycení informací grafiky  
 Teď, když máte platné `IDXGraphicsAnalysis` rozhraní, můžete použít `BeginCapture` a `EndCapture` k zaznamenání grafických informací.  
  
##### <a name="to-capture-graphics-information"></a>K zaznamenání grafických informací  
  
- Spusťte zaznamenání grafických informací pomocí `BeginCapture`:  
  
    ```  
    ...  
    pGraphicsAnalysis->BeginCapture();  
    ...  
    ```  
  
     Zachycení začne okamžitě při `BeginCapture` nazývá; nemá čekat na Další zahájíte rámečku. Zaznamenat zastaví, když se zobrazí aktuální rámečku, nebo když zavoláte `EndCapture`:  
  
    ```  
    ...  
    pGraphicsAnalysis->EndCapture();  
    ...  
    ```  

- Po zavolání `EndCapture`, vydání grafické objekty. 
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukázal, jak k zaznamenání grafických informací prostřednictvím kódu programu. Jako další krok vezměte v úvahu tuto možnost:  
  
-   Zjistěte, jak analyzovat zaznamenané grafických informací pomocí diagnostiky grafiky nástrojů. V tématu [přehled](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Zaznamenání grafických informací](walkthrough-capturing-graphics-information.md)   
 [Zaznamenání grafických informací](capturing-graphics-information.md)   
 [Nástroj příkazového řádku pro zachytávání](command-line-capture-tool.md)