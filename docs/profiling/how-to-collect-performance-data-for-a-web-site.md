---
title: "Postupy: shromažďování dat o výkonu pro webový server | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vsperf.url.url
- vsperf.chooseurl
- vs.performance.wizard.asppage
- vsperf.url.ok
- vsperf.url.cancel
helpviewer_keywords:
- Profiling Tools,profiling ASP.NET
- web sites, performance profiling
- ASP.NET, performance profilng
ms.assetid: a62d27fd-a966-4065-bebe-6874195a71fb
caps.latest.revision: "33"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6acfbee87e64e71ae85290ba74f1464af7181228
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-collect-performance-data-for-a-web-site"></a>Postupy: shromažďování dat o výkonu pro webový server
Můžete použít **Průvodce výkonu** ke shromažďování dat výkonu pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace. Můžete profil webové aplikace, která je otevřen v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], nebo můžete profil [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webu, který je umístěn v místním počítači a není otevřen v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE.  
  
> [!NOTE]
>  **Průvodce výkonu** umožňuje přidání dat interakce (TIP) vrstev, údaje o výkonu JScript nebo na shromážděná data profilování. Možnost TIP shromažďuje data z serverové procesy. Profilace JScript shromažďuje data z skripty, které běží na místním nebo vzdáleném webovém serveru. Ve většině případů měli byste vybrat pouze jednu z možností.  
  
 V závislosti na nastavení přístupová oprávnění uživatelů, které správce má k dispozici jednotlivého uživatele může nebo nemusí mít oprávnění zabezpečení k vytvoření relace profileru na počítači, který je hostitelem procesu ASP.NET. Následující příklady ilustrují možné rozdíly mezi uživateli:  
  
-   Někteří uživatelé přistupovat k pokročilé funkce profilování při správce nastavil ovladače a spuštění služby.  
  
-   Uživatelé domény může přístup k ukázkové profilace jenom.  
  
-   Někteří uživatelé mohou odepřít přístup k profilace všem ostatním uživatelům.  
  
 Další informace najdete v tématu [profilování a zabezpečení systému Windows Vista](../profiling/profiling-and-windows-vista-security.md) a možnosti správce v [VSPerfCmd](../profiling/vsperfcmd.md).  
  
### <a name="to-profile-a-web-site-project"></a>Chcete-li profil webového projektu  
  
1.  Otevřete [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webového projektu v [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] nebo [!INCLUDE[vsUltShort](../code-quality/includes/vsultshort_md.md)].  
  
2.  Na **analyzovat** nabídce vyberte možnost **výkonu profileru**, vyberte **prohlížeč výkonu**a potom vyberte **spustit**.  
  
3.  Na první stránce průvodce vyberte profilování metodu a pak klikněte na tlačítko **Další**. Další informace o metod profilace najdete v tématu [metody kolekce údajů o výkonu Principy](../profiling/understanding-performance-collection-methods.md). Všimněte si, že vizualizér souběžnosti metoda profilování není k dispozici pro webové aplikace.  
  
4.  V **aplikaci, pro kterou chcete cílit pro profilace?** rozevíracího seznamu, ujistěte se, že je vybrána aktuální projekt a pak klikněte na **Další**.  
  
5.  Na třetí stránce průvodce můžete přidat dat interakce vrstev profilování (TIP), data z JavaScript spuštěné v webové stránky, nebo obojí.  
  
    -   Chcete-li shromažďovat sledováním interakce vrstev, vyberte **povolit profilace interakce vrstvy** zaškrtávací políčko.  
  
    -   Chcete-li shromažďovat data z JavaScriptu spuštěné v webové stránky, vyberte **profil JavaScript** zaškrtávací políčko.  
  
6.  Klikněte na tlačítko **Další**.  
  
7.  Na čtvrté stránce průvodce, klikněte na tlačítko **Dokončit**.  
  
8.  Výkonnostní relace se vytvoří pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] spuštění aplikace a webovou stránku v prohlížeči. Prověření funkce, které chcete profil a pak zavřete prohlížeč.  
  
     Profileru generuje datový soubor a zobrazuje souhrnné zobrazení dat v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hlavní okno.  
  
### <a name="to-profile-a-web-site-without-opening-a-project-in-visual-studio"></a>Chcete-li profil webu bez otevření projektu v sadě Visual Studio  
  
1.  Otevřete [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] nebo [!INCLUDE[vsUltShort](../code-quality/includes/vsultshort_md.md)].  
  
2.  Na **analyzovat** nabídce vyberte možnost **výkonu profileru**, vyberte **prohlížeč výkonu**a potom vyberte **spustit**.  
  
3.  Na první stránce průvodce vyberte profilování metodu a pak klikněte na tlačítko **Další**. Další informace najdete v tématu [metody kolekce údajů o výkonu Principy](../profiling/understanding-performance-collection-methods.md).  
  
4.  Na druhé stránce průvodce vyberte **profil aplikace ASP.NET nebo JavaScript** a potom klikněte na **Další**.  
  
5.  V **jaké adresu URL nebo cestu spustí webovou aplikaci** pole na třetí stránce průvodce, zadejte adresu URL na domovskou stránku aplikace a pak klikněte na tlačítko **Další**.  
  
    -   Pro server (IIS) na základě webu, zadejte adresu URL, jako **http://localhost/MySite/default.aspx**. To způsobí, že [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace v místním počítači v kořenovém adresáři aplikace server Chcete-li být profilovaným a default.aspx stránky v dané lokalitě spustit v aplikaci Internet Explorer spusťte relaci.  
  
    -   Pro soubor na základě webu, zadejte cestu, například souboru / / /**c:\WebSites\MySite\default.aspx**. To způsobí, že [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace umístěné v c:\webSites\MySite k být profilovaným a stránky http://localhost:nnnn/MySite/default.aspx spustit v aplikaci Internet Explorer spusťte relaci.  
  
    -   Pro externí servery, které chcete shromažďovat JavaScript data zadejte adresu URL, například http://www.contoso.com.  
  
     Další informace, zobrazení stránek vlastností pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] cílový binární soubor.  
  
6.  Na třetí stránce průvodce můžete přidat dat interakce vrstev profilování (TIP), data z JavaScript spuštěné v webové stránky, nebo obojí.  
  
    -   Chcete-li shromažďovat sledováním interakce vrstev, vyberte **povolit profilace interakce vrstvy** zaškrtávací políčko.  
  
    -   Chcete-li shromažďovat data z JavaScriptu spuštěné v webové stránky, vyberte **profil JavaScript** zaškrtávací políčko.  
  
7.  Klikněte na tlačítko **Další**.  
  
8.  Na čtvrté stránce průvodce, klikněte na tlačítko **Dokončit**.  
  
9. Výkonnostní relace se vytvoří pro aplikace ASP.NET a webový server je spuštěn v prohlížeči. Prověření funkce, které chcete profil a pak zavřete prohlížeč.  
  
     Profileru generuje datový soubor a zobrazuje souhrnné zobrazení dat v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hlavní okno.  
  
## <a name="see-also"></a>Viz také  
 [Přehled](../profiling/overviews-performance-tools.md)   
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Porozumění hodnotám dat instrumentace](../profiling/understanding-instrumentation-data-values.md)   
 [Porozumění hodnotám dat vzorkování](../profiling/understanding-sampling-data-values.md)
