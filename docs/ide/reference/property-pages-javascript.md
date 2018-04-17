---
title: Stránky vlastností, JavaScript | Microsoft Docs
ms.custom: ''
ms.date: 06/21/2017
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- javascript.project.property.debugging.debuggertype
- javascript.project.property.debugging.requireauthentication
- javascript.project.property.outputpath
- javascript.project.property.debugging.launchapplication
- javascript.project.property.defaultlanguage
- javascript.project.property.debugging.machinename
- javascript.project.property.debugging.allowlocalnetworkloopback
ms.assetid: a05ab01f-3d5d-4675-a845-eab51807d3a3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 338ddfe5253c5d4ab148234e8345275620ecac3f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="property-pages-javascript"></a>Stránky vlastností, JavaScript
**Stránky vlastností**poskytuje přístup k nastavení projektu. Stránky, které se zobrazují v můžete použít **stránky vlastností** Chcete-li změnit vlastnosti projektu.  

Pro přístup k vlastnostem projektu, vyberte uzel projektu v **Průzkumníku řešení**. Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  

Následující stránky a možnosti se zobrazí v **stránky vlastností**.  

## <a name="configuration-and-platform-page"></a>Konfigurace a platformy stránky  
 Použijte následující možnosti a vyberte platformu k zobrazení nebo změna a konfigurace.  

 **Konfigurace**  
 Určuje nastavení konfigurace můžete zobrazit nebo upravit. Nastavení jsou **ladění** (výchozí), **verze**, **všechny konfigurace**, nebo vlastní konfiguraci. Další informace najdete v tématu [postupy: nastavení ladění a konfigurace v sadě Visual Studio verze](../../debugger/how-to-set-debug-and-release-configurations.md).  

 **Platforma**  
 Určuje nastavení platformy můžete zobrazit nebo upravit. Nastavení jsou **libovolný procesor** (výchozí pro [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] aplikace), **x64**, **ARM**, **x86**, nebo na uživatelem definované platformě. Další informace najdete v tématu [postupy: nastavení ladění a konfigurace v sadě Visual Studio verze](../../debugger/how-to-set-debug-and-release-configurations.md).  

## <a name="general-page"></a>Obecná stránka  
 Použijte následující možnosti a nastavte obecné vlastnosti projektu.  

> [!NOTE]
>  Některé možnosti jsou dostupné v aplikacích pro UPW jenom.  

 **Výstupní cesta**  
 Určuje umístění výstupní soubory pro konfiguraci projektu. Cesta je relativní; Pokud chcete zadat absolutní cestu, absolutní cesta je uložena v projektu. Výchozí cesta je bin\Debug.  

 Při použití konfigurace zjednodušené sestavení projektu systému určuje, zda sestavování ladění a vydání verze. Když kliknete na tlačítko **ladění**, **spustit ladění** (nebo stiskněte klávesu F5) sestavení je uvést do umístění ladění bez ohledu na to **výstupní cesta** zadáte. Ale **sestavit řešení** příkaz na **sestavení** nabídky vloží ho do umístění, které zadáte. Chcete-li povolit upřesněné konfigurace sestavení, na řádku nabídek zvolte **nástroje**, **možnosti**. V **možnosti** dialogové okno, rozbalte seznam **projekty a řešení**, vyberte **Obecné**a poté zrušte zaškrtnutí **zobrazit Rozšířená konfiguracesestavení**zaškrtávací políčko. To vám dává Ruční kontrola nad všechny hodnoty konfigurace a jestli je založená na verzi ladění nebo verze.  

 **Výchozí jazyk**  
 Určuje výchozí jazyk pro projekt. Jazyk možnosti vybrané v **hodiny, jazyk a oblast** v Ovládacích panelech určuje upřednostňovaný jazyk uživatele. Zadáním výchozí jazyk pro projekt je přesvědčit, aby zadaný výchozí jazyk prostředky se použijí, pokud upřednostňovaný jazyk uživatele neodpovídá jazyk prostředky uvedené v aplikaci.  

## <a name="debug-page"></a>Stránka ladění  
 Pomocí následujících možností pro nastavení vlastností pro ladění chování v projektu.  

> [!NOTE]
>  Některé možnosti jsou dostupné v aplikacích pro UPW jenom.  

 **Ladicí program na spuštění**  
 Určuje výchozí hostitel pro ladicí program.  

-   Vyberte **místního počítače** a spusťte aplikaci v sadě Visual Studio hostitelském počítači. Další informace najdete v tématu [spouštění aplikací v místním počítači](../../debugger/run-windows-store-apps-on-the-local-machine.md).  

-   Vyberte **simulátoru** a spusťte aplikaci v simulátoru. Další informace najdete v tématu [spouštění aplikací v simulátoru](../../debugger/run-windows-store-apps-in-the-simulator.md).  

-   Vyberte **vzdáleného počítače** a spusťte aplikaci ve vzdáleném počítači. Další informace o vzdáleném ladění najdete v tématu [spouštění aplikací ve vzdáleném počítači](../../debugger/run-windows-store-apps-on-a-remote-machine.md).  

**Spuštění aplikace**  
Určuje, zda chcete při stisknutím klávesy F5 nebo klikněte na tlačítko spustit aplikaci **ladění**, **spustit ladění**. Vyberte **Ano** k spustit aplikaci; jinak vyberte možnost **ne**. Pokud vyberete **ne**, můžete stále ladění aplikace, pokud používáte jinou metodu se ho spustit.  

**Typ ladicí program**  
Určuje typy kódu k ladění. Vyberte **pouze skriptu** k ladění kódu jazyka JavaScript. Vyberte **spravovat pouze** chcete ladit kód, který je spravovaný nástrojem modul common language runtime. Vyberte **pouze nativní** k ladění kódu C++. Vyberte **nativní pomocí skriptu** k ladění C++ a JavaScript. Vyberte **Mixed (spravované a nativní)** ladění i spravované a C++ – kód.  

**Povolit zpětnou smyčku místní sítě**  
Určuje, zda je povolen přístup na IP adresu zpětné smyčky pro testování aplikace. Vyberte **Ano** Pokud chcete povolit použití adresu zpětné smyčky Pokud je klient aplikace na stejném počítači kde je serverová aplikace spuštěné; jinak, **ne**. Tato vlastnost je k dispozici pouze v případě **ladicí program na spuštění** je nastavena na **vzdáleného počítače**.  

**Název počítače**  
Určuje název vzdáleného počítače pro hostování ladicího programu. Tato vlastnost je k dispozici pouze v případě **ladicí program na spuštění** je nastaven na **vzdáleného počítače**.  

**Vyžadovat ověřování**  
Určuje, zda vzdálený počítač vyžaduje ověření. Tato vlastnost je k dispozici pouze v případě **ladicí program na spuštění** je nastaven na **vzdáleného počítače**.
