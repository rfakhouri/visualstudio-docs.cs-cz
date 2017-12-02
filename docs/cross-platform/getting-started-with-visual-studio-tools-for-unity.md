---
title: "Začínáme s nástroji Visual Studio Tools for Unity | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 66b5b4eb-13b5-4071-98d2-87fafa4598a8
caps.latest.revision: "10"
author: conceptdev
ms.author: crdun
manager: crdun
ms.openlocfilehash: 1727330a559b5a9aed41ea9063f3394e01bc45ab
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/29/2017
---
# <a name="getting-started-with-visual-studio-tools-for-unity"></a>Začínáme s nástroji Visual Studio Tools for Unity
V této části se dozvíte, jak nainstalovat Visual Studio Tools for Unity a nakonfigurujete svůj projekt Unity pro práci s Visual Studio.  

> [!IMPORTANT]
>  Unity 5.2 přidá integrovanou podporu pro Visual Studio Tools pro Unity 2.1, která zjednodušuje nastavení projektu. Abyste mohli využívat tohoto, budete potřebovat Unity verze 5.2.0 nebo vyšší na systém Windows a Visual Studio Tools for Unity verze 2.1 nebo vyšší.  

## <a name="prerequisites"></a>Požadavky  
 Chcete-li použít Visual Studio Tools for Unity, budete potřebovat:  

-   Verzi **Visual Studio** podporující rozšíření, jako je například Visual Studio Community, Professional, Premium nebo Enterprise. Visual Studio Community si můžete stáhnout zdarma.  

     [Stáhněte si Visual Studio Community](http://www.visualstudio.com/downloads/download-visual-studio-vs)  

-   **Unity** verze 4.0.0 nebo novější; **Unity** verze 5.2.0 nebo vyšší využít integrovanou podporu pro Visual Studio Tools for Unity verze 2.1 nebo vyšší.  

     [Stáhnout Unity](https://unity3d.com/get-unity/download)  

## <a name="install-visual-studio-tools-for-unity"></a>Instalace nástrojů Visual Studio Tools for Unity  
 Stáhněte a nainstalujte Visual Studio Tools for Unity z Galerie Visual Studio. Budete potřebovat k instalaci správné balíčku pro vaši verzi sady Visual Studio. Ujistěte se, že jste nainstalovali Visual Studio Tools for Unity verze 2.1 nebo vyšší využít integrovanou podporu pro VSTU v Unity 5.2 nebo vyšší.  

-   Pro Visual Studio 2015 Community, Visual Studio 2015 Professional nebo Visual Studio 2015 Enterprise:  

     [Stáhněte si Visual Studio 2015 Tools for Unity](https://visualstudiogallery.msdn.microsoft.com/8d26236e-4a64-4d64-8486-7df95156aba9)  

-   Pro Visual Studio 2013 Community, Visual Studio 2013 Professional nebo Visual Studio 2013 Premium:  

     [Stáhněte si Visual Studio 2013 Tools for Unity](https://visualstudiogallery.msdn.microsoft.com/20b80b8c-659b-45ef-96c1-437828fe7cf2)  

-   Pro Visual Studio 2012 Professional nebo Visual Studio 2012 Premium:  

     [Stáhněte si Visual Studio 2012 Tools for Unity](https://visualstudiogallery.msdn.microsoft.com/7ab11d2a-f413-4ed6-b3de-ff1d05157714)  

-   Pro Visual Studio 2010 Professional nebo Visual Studio 2010 Premium:  

     [Stáhněte si Visual Studio 2010 Tools for Unity](https://visualstudiogallery.msdn.microsoft.com/6e536faa-ce73-494a-a746-6a14753015f1)  

> [!NOTE]
>  Expresní verze sady Visual Studio nepodporují rozšíření, jako je například Visual Studio Tools for Unity. Visual Studio Community je bezplatnou verzi Visual Studia, která podporuje Visual Studio Tools for Unity a další rozšíření. Visual Studio Community pro většinu uživatelů, je vhodnější než Express.  

> [!NOTE]
>  Pro Visual Studio 2017 VSTU 3 obsahuje Unity zatížením, které můžete vybrat z instalační služby.  

## <a name="your-first-unity-project-with-visual-studio-tools-for-unity"></a>Svůj první projekt Unity s nástroji Visual Studio Tools for Unity  
 Teď, když máte všechny potřebné, jste připraveni svůj první projekt Unity pomocí sady Visual Studio. Nastavení projektu Unity se liší podle toho, jaké verze Unity a Visual Studio Tools for Unity jsou nainstalovány. Postupujte podle kroků pro verzi Unity a Visual Studio Tools for Unity, který jste nainstalovali.  

### <a name="unity-52-and-higher-requires-vstu-21-or-higher"></a>Unity 5.2 a vyšší (vyžaduje VSTU 2.1 nebo vyšší)  
 Od verze Unity 5.2, už máte pro import nástroje sady Visual Studio unitypackage do vašich projektů. Pokud váš projekt naimportuje tento unitypackage, Unity 5.2 ji ignoruje a přímo načte Visual Studio Tools for Unity z jeho umístění instalace.  

#### <a name="1---create-a-unity-project"></a>1 – Vytvoření projektu Unity  
 Pokud již máte zkušenosti s Unity, můžete vytvořit nový projekt nebo vlastním načíst. Pokud načítáte projekt, který importovat unitypackage nástroje sady Visual Studio používat Visual Studio Tools for Unity s předchozí verzí Unity, doporučujeme odebrat odstraněním adresáři UnityVS.  

 Jinak Pokud jste ještě Unity, začněte v malém rozsahu s základní kurzu. Navštivte stránku Unity další kurzy v příkladu projekty, které můžete spustit v a lekce, které se dozvíte z vytvořit svoji vlastní hru s Unity. Stránka Další Unity má snadno podle kurzy pro několik různých hry.  

 [Kurzy – stránka Další Unity](http://unity3d.com/learn/tutorials/modules)  

#### <a name="2---configure-unity-editor-to-use-visual-studio-tools-for-unity"></a>2 – konfigurace editoru Unity používat Visual Studio Tools for Unity  
 Pokud chcete povolit projektu pro použití Visual Studio Tools for Unity, stačí nastavte Visual Studio jako editor externího skriptu. V programu editoru Unity v hlavní nabídce zvolte **Předvolby úprav**; potom v **Unity Předvolby** dialogovém okně, vyberte **externí nástroje**. Dále nastavte **Editor skriptů externí** vlastnost, která má verzi Visual Studia, kterou chcete použít (Visual Studio Tools for Unity musí být nainstalována pro tuto verzi sady Visual Studio) a zajistěte, aby **Editor připojení** je nastavena.  

 Chcete-li mít jistotu, že integrovanou podporu pro Visual Studio Tools pro Unity je teď povolené, přečtěte si téma **o Unity** dialogové okno. V editoru Unity v hlavní nabídce zvolte **pomoci, o Unity.** Pokud Visual Studio Tools for Unity nainstalovaná a správně nakonfigurovaná, zobrazí se zpráva zobrazí v levém dolním rohu **o Unity** dialogové okno.  

 Nakonec se ujistěte, nastavíte cíl sestavení prostřednictvím **nastavení sestavení** stránky a že **ladění skriptů** je povoleno.  

 ![Nakonfigurujte nastavení Unity sestavení pro ladění. ] (../cross-platform/media/vstu_debugging_build_settings.png "vstu_debugging_build_settings")  

#### <a name="3---launch-visual-studio-from-the-unity-editor"></a>3 – Spusťte sadu Visual Studio z editoru Unity  
 Od verze Unity 5.2 **nástroje sady Visual Studio** nabídka rozšíření se už nepotřebuje, spusťte sadu Visual Studio nebo Visual Studio Tools for Unity konfigurace. Místo toho jednou Visual Studio je nakonfigurován jako editor externího skriptu, stačí vybrat soubor skriptu z editoru Unity a kódu se otevřou v sadě Visual Studio.  

### <a name="previous-versions-of-unity-pre-52"></a>Předchozí verze Unity (pre-5.2)  
 Před Unity 5.2 byl žádné integrovanou podporu pro Visual Studio Tools for Unity. Místo toho každý projekt bylo nutné importovat unitypackage nástroje sady Visual Studio a nakonfigurujte další nastavení projektu, aby bylo možné používat Visual Studio Tools for Unity.  

#### <a name="1---create-a-unity-project"></a>1 – Vytvoření projektu Unity  
 Pokud již máte zkušenosti s Unity, můžete vytvořit nový projekt nebo vlastním načíst. Pokud začínáte nový projekt, importujte unitypackage nástroje sady Visual Studio při jeho vytvoření.  

 Jinak Pokud jste ještě Unity, začněte v malém rozsahu s základní kurzu. Navštivte stránku Unity další kurzy v příkladu projekty, které můžete spustit v a lekce, které se dozvíte z vytvořit svoji vlastní hru s Unity. Stránka Další Unity má snadno podle kurzy pro několik různých hry.  

 [Kurzy – stránka Další Unity](http://unity3d.com/learn/tutorials/modules)  

#### <a name="2---configure-unity-editor-to-use-visual-studio-tools-for-unity"></a>2 – konfigurace editoru Unity používat Visual Studio Tools for Unity  
 Pokud se od existujícího projektu Unity nebo nebyla importujete unitypackage nástroje sady Visual Studio, když vytvoříte projekt, budete muset importovat unitypackage nyní. V editoru Unity v hlavní nabídce zvolte **prostředky, importovat balíček, nástroje sady Visual Studio 2015** (měli vidět možnost pro verzi mít nainstalovanou sadu Visual Studio).  

 ![Importujte balíčku VSTU do projektu Unity. ] (../cross-platform/media/vstu_configure_unity_import_vstu.png "vstu_configure_unity_import_vstu")  

 Nakonec se ujistěte, nastavíte cíl sestavení prostřednictvím **nastavení sestavení** stránky a že **ladění skriptů** je povoleno.  

 ![Nakonfigurujte nastavení Unity sestavení pro ladění. ] (../cross-platform/media/vstu_debugging_build_settings.png "vstu_debugging_build_settings")  

#### <a name="3---launch-visual-studio-from-unity-editor"></a>3 – Spusťte sadu Visual Studio z editoru Unity  
 Posledním krokem je spuštění sady Visual Studio z Unity. To vytvoří řešení sady Visual Studio pro projekt a pak ho otevře v sadě Visual Studio.  

 V programu editoru Unity v hlavní nabídce zvolte **nástroje sady Visual Studio, otevřete v sadě Visual Studio**.  

 ![Otevřete projekt unity v sadě Visual Studio. ] (../cross-platform/media/vstu_configure_open_in_visual_studio.png "vstu_configure_open_in_visual_studio")  

## <a name="next-steps"></a>Další kroky  

 Naučte se pracovat a spusťte ladění svého projektu Unity v sadě Visual Studio, najdete v tématu [pomocí Visual Studio Tools for Unity](../cross-platform/using-visual-studio-tools-for-unity.md).  

## <a name="see-also"></a>Viz také  
 [Domovská stránka Unity](http://unity3d.com)
