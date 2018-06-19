---
title: Import projektu XCode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: aa4b8161-d98f-4a1a-9db3-520133bfc82f
ms.technology: vs-ide-mobile
author: corob-msft
ms.author: corob
manager: douge
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 500dce15e695cf53a061f8405919e808b8f7c493
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31066935"
---
# <a name="import-an-xcode-project"></a>Import projektu XCode
Microsoft Visual C++ pro vývoj mobilních řešení pro různé platformy zahrnuje podporu pro přesun projekty XCode do sady Visual Studio, kde můžete vytvořit knihovny napříč platformami a sdílet s jinými projekty kódu. XCode Průvodce importem zjednodušuje proces import projektů a rozdělení out kódu C++ v vaše cíle XCode pro použít jako statické knihovny nebo sdílené kód projektu. Můžete spravovat specifické pro iOS kódu v sadě Visual Studio a stále proveďte scénářů a sestavení pomocí XCode. Informace o tom, jak snadno přesunout přepínat mezi sadou Visual Studio a XCode kódu najdete v tématu přesunout změny mezi XCode a Visual Studio.  
  
## <a name="using-the-import-from-xcode-wizard"></a>Pomocí Průvodce importem z XCode  
 Toto téma ukazuje, jak přesunout do sady Visual Studio využívat výhod sdílení kódu a řešení pro různé platformy projektu XCode. Předpokladem je musí spárujte počítači Mac k sadě Visual Studio, abyste mohli importovat, exportovat a sestavení projektu. Pokyny o tom, jak nastavit párování najdete v tématu [instalaci a konfiguraci nástroje pro sestavení pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md). Musíte také sdílet projektu XCode přes síť nebo ho přesunout do počítače Visual Studio pro používání XCode Průvodce importem.  
  
#### <a name="import-from-xcode"></a>Importovat z XCode  
  
1.  Na **soubor** nabídce zvolte **nový**, **Import**, **importovat z XCode**. Tím se spustí **importovat z XCode** dialogové okno průvodce.  
  
     ![Vyberte cílový projekt XCode pro import](../cross-platform/media/cppmdd_u2_importxcode_choose.PNG "CPPMDD_U2_ImportXCode_Choose")  
  
2.  V **zvolit projekt** podokně klikněte na tlačítko Procházet a vyberte soubor .pbxproj XCode. Přejděte k souboru projektu v **soubor projektu XCode vyberte** dialogové okno a potom zvolte **otevřete**.  
  
     ![Vyberte soubor projektu v dialogovém okně vyberte Xcode projektu soubor](../cross-platform/media/cppmdd_u2_importxcode_browse.PNG "CPPMDD_U2_ImportXCode_Browse")  
  
     V XCode Průvodce importem, zvolte **Další**.  
  
3.  V **cílové cíle** podokně zvolte cíle z projektu XCode k importu do projektů sady Visual Studio. XCode cíle jsou podobná projektů sady Visual Studio; Většina jsou kolekce kódu a prostředky, které vytvářejí binární. XCode Průvodce importem pouze umožňuje import cílů, které produkují binární, ale není statickou knihovnu, jako cílový cíle. XCode statické knihovny cíle jsou předmětem dalším krokem.  
  
     ![Importovat z okna cílové cíle Průvodce XCode](../cross-platform/media/cppmdd_u2_importxcode_destination.jpg "CPPMDD_U2_ImportXCode_Destination")  
  
     Pro každý cíl vybraný v **cíle pro import**, průvodce automaticky zjišťuje soubory kódu C++, které je možné rozdělit na samostatné statické knihovny projektu a umístí je do **položky projektu C++** části. Další kód a prostředky jsou ponechána na **položky projektu XCode** části. Tyto stát samostatné statickou knihovnou a aplikace projekty v sadě Visual Studio po dokončení procesu importu. Ve výchozím nastavení nejsou jednotky test a framework cíle rozdělit na samostatné projekty průvodcem.  
  
     Chcete-li změnit soubory, které jsou v každém projektu, nahoru a dolů. Jakmile budete spokojeni se soubory v každém projektu, zvolte **Další** pokračujte.  
  
4.  V **knihovny cíle** podokně, vyberte, které statické knihovny cílem z projektu XCode k importu do projektů sady Visual Studio. V tomto podokně můžete soubory, které jsou umístěny v projektu sdíleného kódu a které jsou umístěny v projektu statické knihovny. V každé z cílů v **cíle pro import** seznamu, můžete řídit, které soubory jsou umístěny v **položky projektu sdíleného kódu** a **položky projektu statické knihovny** pomocí tlačítka nahoru a dolů.  
  
     ![Importovat z knihovny cíle XCode podokně](../cross-platform/media/cppmdd_u2_importxcode_library.jpg "CPPMDD_U2_ImportXCode_Library")  
  
     Projektu sdíleného kódu je způsob sdílení sadu soubory zdrojového kódu mezi projekty v sadě Visual Studio. Kód je sestaven jako součást projekt, který ji obsahuje, ne jako vlastní projektu. Protože projekty, které zahrnují kód sdílený může mít různé architektury a konfigurace, toto je nejlepší způsob, jak poskytnout jeden projekt, který obsahuje kód, který může být vytvořená pro různé druhy platformy.  
  
     Jakmile budete spokojeni se soubory v každém projektu, zvolte **Další** pokračujte.  
  
5.  **Vlastnosti globálních** podokně můžete použít k nastavení cestu framework vyhledávání a cesta k zahrnutí záhlaví vyhledávání pro všechny projekty iOS v sadě Visual Studio. Visual Studio použije tyto cesty pro procházení zdrojového kódu a technologii IntelliSense. Tyto globální cesty jsou užitečné, když vytvoříte iOS projekty, které používají společnou sadu hlaviček a rozhraní.  
  
     ![Importovat z podokna globální vlastnosti XCode](../cross-platform/media/cppmdd_u2_importxcode_global.jpg "CPPMDD_U2_ImportXCode_Global")  
  
     Tyto globální cesty lze také nastavit v sadě Visual Studio v **možnosti** dialogové okno. K dispozici, na **nástroje** nabídce vyberte možnost **možnosti**. V **možnosti** dialogové okno, rozbalte položku **křížové platformy**, **C++**, **iOS**, **vlastnosti globálních**.  
  
     Zvolte **Další** pokračujte.  
  
6.  **Rozhraní** podokně slouží ke konfiguraci cesty využívá sada Visual Studio pro procházení a technologii IntelliSense pro váš projekt. Cesty musí být přístupné pro Visual Studio pro každou platformu odkazuje projektu XCode. Průvodce zkontroluje rozhraní odkazuje v projekty XCode a zobrazuje, zda Visual Studio můžete najít rozhraní. Jakoukoli cestu, kterou už jste nastavili ve vlastnostech globální by měly být zjištěny pomocí sady Visual Studio. Výjimky jsou uvedeny v seznamu architektury. Pro každou platformu označené X zadejte cestu, dostupný počítač pro sadu Visual Studio k vyhledání rozhraní. Na tlačítko Procházet [...] můžete použít **vyberte složku** dialogovém okně můžete najít cestu. Framework cesta může být buď místní kopii, nebo do sdílené složky přístupné prostřednictvím sítě na vaše Mac.  
  
     ![Importovat z podokna XCode rozhraní](../cross-platform/media/cppmdd_u2_importxcode_frameworks.jpg "CPPMDD_U2_ImportXCode_Frameworks")  
  
     Zvolte **Další** pokračujte.  
  
7.  **Nastavení projektu** podokně umožňuje změnit framework a zahrnují nastavení cesty hledání záhlaví pro každý projekt, Průvodce vytvoří. V tomto podokně slouží k nastavení projektu konkrétní cesty, které se liší od globální nastavení.  
  
     V nastavení cesty pro konkrétní projekt, **cílové projektu** rozevíracího seznamu, vyberte soubor projektu a pak nastavte hodnoty **cesty pro hledání Framework** a **obsahovat záhlaví cesty pro hledání** ovládací prvky. Můžete použít tlačítko procházení [...] vedle každý ovládací prvek použít **vyberte složku** dialogovém okně můžete najít cestu.  
  
     ![Importovat z podokna projekty XCode](../cross-platform/media/cppmdd_u2_importxcode_projects.jpg "CPPMDD_U2_ImportXCode_Projects")  
  
     Pokud žádné vzdálené Mac má byl spárován s Tento počítač v sadě Visual Studio, konfigurací vzdáleném počítači propojení se zobrazí. Pokyny o tom, jak nastavit párování najdete v tématu [instalaci a konfiguraci nástroje pro sestavení pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md).  
  
     Chcete-li importovat projekt XCode pomocí nastavení v průvodci, zvolte **importovat**.  
  
 XCode Průvodce importem vytvoří projekty v sadě Visual Studio, která odpovídají vybrané cíle projektu XCode. Kód, který je možné sdílet s jinými projekty C++ je rozdělit na samostatné sdíleného kódu a projektů statické knihovny. Zbývající kód je umístěn v iOS knihovny a aplikace projekty, které mohou být vytvořeny vzdáleně pomocí sady Visual Studio. Další informace o přesunutí kód mezi sadou Visual Studio a XCode najdete v tématu [synchronizace změn mezi XCode a Visual Studio](../cross-platform/sync-changes-between-xcode-and-visual-studio.md).