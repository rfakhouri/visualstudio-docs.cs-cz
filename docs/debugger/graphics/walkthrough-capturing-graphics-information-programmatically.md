---
title: "Návod: Zaznamenání grafických informací prostřednictvím kódu programu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5adeff9-afaf-4047-b5ce-ef0aefe710eb
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 59853bf733364f2db8a60e3c9515e2771c8e4ebe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-capturing-graphics-information-programmatically"></a>Návod: Zaznamenání grafických informací prostřednictvím kódu
Můžete použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] diagnostiky grafiky k prostřednictvím kódu programu zaznamenání grafických informací z aplikace Direct3D.  
  
 Zachytávání prostřednictvím kódu programu je užitečný ve scénářích, jako například:  
  
-   Začněte zachytávání prostřednictvím kódu programu, až aplikace grafiky nepoužívá swapchain existuje, například když vykresluje texturou.  
  
-   Začněte zachytávání prostřednictvím kódu programu, až aplikace nemá vykreslení vůbec, například když používá DirectCompute k provádění výpočtů.  
  
-   Volání `CaptureCurrentFrame`při vykreslování problém je obtížné předvídat a zaznamenat v manuálním testováním, ale můžete pomocí informací o stavu aplikace za běhu prostřednictvím kódu programu předpovědět.  
  
##  <a name="CaptureDX11_2"></a>Zachytávání prostřednictvím kódu programu ve Windows 8.1  
 Tato část průvodce ukazuje zachytávání prostřednictvím kódu programu v aplikacích, které používají rozhraní API 11.2 DirectX na Windows 8.1, která používá metodu robustní zachycení. Informace o tom, jak použít zachytávání prostřednictvím kódu programu v aplikacích, které používají starší verze rozhraní DirectX v systému Windows 8.0 najdete v tématu [zachytávání prostřednictvím kódu programu Windows 8.0 a starší](#CaptureDX11_1) dále v tomto návodu.  
  
 V této části ukazuje, jak provést tyto úlohy:  
  
-   Příprava aplikace použít zachytávání prostřednictvím kódu programu  
  
-   Získání rozhraní IDXGraphicsAnalysis  
  
-   Zachycení informací grafiky  
  
> [!NOTE]
>  Předchozích implementacích zachytávání prostřednictvím kódu programu spoléhali na nástroje pro vzdálenou pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] pro zajištění zachycení, Windows 8.1 podporuje zachycení přímo přes Direct3D – 11.2. V důsledku toho již máte k instalaci nástrojů pro vzdálenou pro zachytávání prostřednictvím kódu programu na Windows 8.1.  
  
### <a name="preparing-your-app-to-use-programmatic-capture"></a>Příprava aplikace použít zachytávání prostřednictvím kódu programu  
 Pokud chcete použít zachytávání prostřednictvím kódu programu ve vaší aplikaci, musí obsahovat potřebné hlavičky. Tyto hlavičky jsou součástí sady SDK pro Windows 8.1.  
  
##### <a name="to-include-programmatic-capture-headers"></a>Chcete-li patří hlavičky zachytávání prostřednictvím kódu programu  
  
-   Zdrojový soubor, ve které definujete rozhraní IDXGraphicsAnalysis zahrňte tyto hlavičky:  
  
    ```  
    #include <DXGItype.h>  
    #include <dxgi1_2.h>  
    #include <dxgi1_3.h>  
    #include <DXProgrammableCapture.h>  
    ```  
  
    > [!IMPORTANT]
    >  Nezahrnovat záhlaví souboru vsgcapture.h—which podporuje zachytávání prostřednictvím kódu programu na Windows 8.0 a starší – provádět zachytávání prostřednictvím kódu programu v aplikacích Windows 8.1. Tuto hlavičku není kompatibilní s DirectX 11.2. Pokud tento soubor je zahrnuto po zahrnuté hlavičku d3d11_2.h, vydá upozornění. Pokud vsgcapture.h je zahrnutý před d3d11_2.h, aplikace se nespustí.  
  
    > [!NOTE]
    >  Pokud 2010 června DirectX SDK je v počítači nainstalován a obsahuje cesta zahrnutí vašeho projektu `%DXSDK_DIR%includex86`, ho přesunout na konec cesty zahrnutí. Totéž pro vaši cestu knihovny.  
  
#### <a name="windows-phone-81"></a>Windows Phone 8,1  
 Protože Windows Phone 8.1 SDK nezahrnuje hlavičky DXProgrammableCapture.h, budete muset definovat `IDXGraphicsAnalysis` rozhraní sami, takže můžete použít `BeginCapture()` a `EndCapture()` metody. Zahrnout další hlavičky, jak je popsáno v předchozí části.  
  
###### <a name="to-define-the-idxgraphicsanalysis-interface"></a>Chcete-li definovat rozhraní IDXGraphicsAnalysis  
  
-   Definujte rozhraní IDXGraphicsAnalysis do stejného souboru, která obsahuje soubory hlaviček.  
  
    ```  
    interface DECLSPEC_UUID("9f251514-9d4d-4902-9d60-18988ab7d4b5") DECLSPEC_NOVTABLE  
    IDXGraphicsAnalysis : public IUnknown  
    {  
        STDMETHOD_(void, BeginCapture)() PURE;  
        STDMETHOD_(void, EndCapture)() PURE;  
    };  
    ```  
  
 Pro větší pohodlí si můžete proveďte tyto kroky v nový soubor záhlaví a pak ji kde je třeba zahrnout do vaší aplikace.  
  
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
  
     Nezapomeňte se podívat `HRESULT` vrácený `DXGIGetDebugInterface1` zajistit získat platný rozhraní dříve, než ho použijete:  
  
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
  
-   Spusťte zaznamenání grafických informací pomocí `BeginCapture`:  
  
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
  
##  <a name="CaptureDX11_1"></a>Zachytávání prostřednictvím kódu programu Windows 8.0 a starší  
 Tato část průvodce ukazuje zachytávání prostřednictvím kódu programu v aplikace pro Windows 8.0 a starší, které používají rozhraní DirectX 11.1 API, které používá metodu starší verze zachycení. Informace o tom, jak použít zachytávání prostřednictvím kódu programu v aplikacích, které používají rozhraní DirectX 11.2 na Windows 8.1 najdete v tématu [Programmatic zaznamenat ve Windows 8.1](#CaptureDX11_2) výše v tomto návodu.  
  
 Tato část uvádí tyto úlohy:  
  
-   Příprava počítače pro používání zachytávání prostřednictvím kódu programu  
  
-   Příprava aplikace použít zachytávání prostřednictvím kódu programu  
  
-   Konfigurace názvu a umístění souboru protokolu grafiky  
  
-   Pomocí `CaptureCurrentFrame` rozhraní API  
  
### <a name="preparing-your-computer-to-use-programmatic-capture"></a>Příprava počítače pro používání zachytávání prostřednictvím kódu programu  
 Zachytávání prostřednictvím kódu programu rozhraní API pomocí nástrojů pro vzdálenou pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nakonfigurovánu zachycení. Počítače, kde bude spuštěna aplikace musí mít nástrojů pro vzdálenou nainstalovaná, i když používáte zachytávání prostřednictvím kódu programu v místním počítači. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]nemusí být spuštěn, když provádíte zachytávání prostřednictvím kódu programu na místním počítači.  
  
 Pokud chcete použít vzdálenou zachycení rozhraní API v aplikaci, která je spuštěná na počítači, nejprve musíte nainstalovat nástroje pro vzdálenou pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] na tomto počítači. Různé verze nástrojů pro vzdálenou podporu různých hardwarových platforem. Informace o tom, jak nainstalovat nástroje pro vzdálenou najdete v tématu [stránce pro stažení nástroje pro vzdálenou](http://go.microsoft.com/fwlink/p/?LinkId=246691) na Microsoft webu pro stahování.  
  
 Alternativně [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nainstaluje komponenty potřebné k provedení vzdálené zachycení pro 32bitové aplikace.  
  
> [!NOTE]
>  Protože většina aplikacích klasické pracovní plochy Windows – včetně [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]– nepodporuje [!INCLUDE[win8](../includes/win8_md.md)] pro zařízení s ARM, pomocí nástrojů pro vzdálenou pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] společně s zachytávání prostřednictvím kódu programu rozhraní API je jediný způsob, jak zachycení diagnostiky grafiky na zařízeních ARM.  
  
### <a name="preparing-your-app-to-use-programmatic-capture"></a>Příprava aplikace použít zachytávání prostřednictvím kódu programu  
 Při použití nástroje pro diagnostiky grafiky, musíte nejprve zaznamenání grafických informací, na kterém je závislý. Informace můžete zaznamenat programově pomocí `CaptureCurrentFrame` rozhraní API.  
  
##### <a name="to-prepare-your-app-to-capture-graphics-information-programmatically"></a>Příprava aplikace k zaznamenání grafických informací prostřednictvím kódu programu  
  
1.  Ujistěte se, že `vsgcapture.h` záhlaví je součástí zdrojového kódu pro aplikaci. Můžou být součástí jen jedno umístění – například v souboru zdrojového kódu, kde bude volat programový zaznamenat rozhraní API – nebo v předkompilovaný hlavičkový soubor pro volání rozhraní API z více zdrojových souborů s kódy.  
  
2.  Ve zdrojovém kódu aplikace, kdykoli budete chtít zachytit zbytek aktuální rámečku, volání `g_pVsgDbg->CaptureCurrentFrame()`. Tato metoda nepřijímá žádné parametry a nevrací hodnotu.  
  
### <a name="configuring-the-name-and-location-of-the-graphics-log-file"></a>Konfigurace názvu a umístění souboru protokolu grafiky  
 Grafika protokolu se vytvoří v umístění, které je definované `DONT_SAVE_VSGLOG_TO_TEMP` a `VSG_DEFAULT_RUN_FILENAME` makra.  
  
##### <a name="to-configure-the-name-and-location-of-the-graphics-log-file"></a>Chcete-li konfigurovat název a umístění souboru protokolu grafiky  
  
-   Protokol grafiky zabránit před zápisem do dočasného adresáře `#include <vsgcapture.h>` řádek, přidejte následující:  
  
    ```  
    #define DONT_SAVE_VSGLOG_TO_TEMP  
    ```  
  
     Můžete definovat tuto hodnotu zapisovat protokolu grafiky do umístění, která je relativní vzhledem k pracovní adresář, nebo na absolutní cestu, pokud definice `VSG_DEFAULT_RUN_FILENAME` je absolutní cesta.  
  
-   Chcete uložit protokol grafiky do jiného umístění nebo pojmenujte ho jiný soubor, než `#include <vsgcapture.h>` řádek, přidejte následující:  
  
    ```  
    #define VSG_DEFAULT_RUN_FILENAME <filename>  
    ```  
  
     Pokud nemáte-li provést tento krok, název souboru je default.vsglog. Pokud neuvedli `DONT_SAVE_VSGLOG_TO_TEMP`, pak umístění souboru je relativní vzhledem k dočasnému adresáři; jinak, je relativní vzhledem k pracovní adresář nebo v jiném umístění. Pokud jste zadali absolutního názvu souboru.  
  
 Pro [!INCLUDE[win8_appname_long](../includes/win8_appname_long_md.md)] aplikace, umístění dočasné složky je specifický pro každého uživatele a aplikace a se většinou nachází v umístění, třeba C:\users\\*uživatelské jméno*\AppData\Local\Packages\\ *pfn*\TempState\\. Aplikací klasické pracovní plochy, umístění dočasné složky je specifický pro každého uživatele a se většinou nachází v umístění, třeba C:\Users\\*uživatelské jméno*\AppData\Local\Temp\\.  
  
> [!NOTE]
>  Zápis do určitého umístění, musí mít oprávnění k zápisu do tohoto umístění; v opačném případě dojde k chybě. Mějte na paměti, [!INCLUDE[win8_appname_long](../includes/win8_appname_long_md.md)] aplikace jsou omezeny více než aplikace klasické pracovní plochy o kde lze zapisovat a může vyžadovat další konfiguraci k zápisu do určitých umístění.  
  
### <a name="capturing-the-graphics-information"></a>Zaznamenání grafických informací  
 Po aplikace připravené pro zachytávání prostřednictvím kódu programu a volitelně nakonfigurovaný umístění a název grafiky soubor protokolu, sestavení aplikace a pak spusťte nebo ladění ho k zaznamenání dat; Nespouštět diagnostiky grafiky z [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] při použití zachytávání prostřednictvím kódu programu rozhraní API. Grafika protokol je zapsán do umístění, které jste zadali. Pokud chcete zachovat tuto verzi protokolu, ho přesunete do jiného umístění; jinak budou přepsány při dalším spuštění aplikace.  
  
> [!TIP]
>  Můžete stále zaznamenání grafických informací ručně při používání zachytávání prostřednictvím kódu programu – s aplikací v fokus, stačí stisknout klávesu **Print Screen**. Tento postup slouží k zaznamenání informací další grafiky, který není zachycenou zachytávání prostřednictvím kódu programu rozhraní API.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukázal, jak k zaznamenání grafických informací prostřednictvím kódu programu. Jako další krok vezměte v úvahu tuto možnost:  
  
-   Zjistěte, jak analyzovat zaznamenané grafických informací pomocí diagnostiky grafiky nástrojů. V tématu [přehled](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Zaznamenání grafických informací](walkthrough-capturing-graphics-information.md)   
 [Zaznamenání grafických informací](capturing-graphics-information.md)   
 [Nástroj příkazového řádku zachycení](command-line-capture-tool.md)