---
title: "Vědecké zpracování dat a analytických aplikací úloh v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 09/05/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
- devlang-python
- devlang-fsharp
ms.tgt_pltfrm: 
ms.topic: landing-page
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 014d0ecef725f425694c231048d31688ec5a59ea
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="data-science-and-analytical-applications-workload"></a>Vědecké zpracování dat a analytických aplikací pracovního vytížení

Zatížení vědecké zpracování dat a analytických aplikací v sadě Visual Studio spojuje tři jazyky a jejich odpovídajících runtime distribuce:

- [R a klient Microsoft R](../rtvs/index.md)
- [Python a Anaconda](../python/python-in-visual-studio.md)
- [F # s použitím rozhraní .NET framework](https://docs.microsoft.com/dotnet/fsharp/)

![Vědecké zpracování dat a aplikací analýzy zatížení v instalačním programu sady Visual Studio](media/data-science-workload.png)

Dva primární skriptovací jazyky používané pro vědecké zpracování dat se R a Python. Oba jazyky jsou snadno další a podporuje bohatý ekosystém balíčků. Tyto balíčky adres širokou škálu scénáře, jako je získávání dat, čištění, školení modelu, nasazení a vykreslení. A F # je výkonný jazyk funkční první rozhraní .NET, který je vhodný pro širokou škálu úloh zpracování dat.

<!--Note link on the image because this one is large -->
[![Snímky obrazovky sady Visual Studio s R, Python a F #](media/data-science-workload-screens.png)](media/data-science-workload-screens.png)

## <a name="workload-options"></a>Možnosti pracovního vytížení

Ve výchozím nastavení nainstaluje zatížení následující možnosti, které můžete upravit v části souhrnu pro pracovní vytížení v instalačním programu sady Visual Studio:

- Podpora jazyka F #
- Jazyk Python:
  - Podpora jazyka Python
  - Podpora webového Python
  - [Anaconda3 64-bit](https://www.continuum.io) (distro A Python, která obsahuje překladač Pythonu a vědecké účely knihovny rozsáhlého datového)
  - Podpora Cookiecutter šablony
- R:
  - Podpora jazyka R
  - [R klienta Microsoft](/machine-learning-server/r-client/what-is-microsoft-r-client) (společnosti Microsoft plně kompatibilní, podporované komunity R překladač s knihovnami ScaleR pro rychlejší výpočty na jednom uzlů nebo clustery. Můžete použít také všechny R z [CRAN](https://cran.r-project.org/).)
  - Podpora modulu runtime pro nástroje pro vývoj R

I když F # je součástí několika dalších zatížení a Python má zatížení svůj vlastní, vědecké zpracování dat a aplikací pro uchovávání pouze úlohy v současné době je zahrnující R. bez ohledu na zatížení, tři komponenty R jsou také volitelný na  **Jednotlivé komponenty** kartě v instalačním programu. Vyberte možnosti **vývoj aktivity > R jazyková podpora**, **vývoj aktivity > R klienta Microsoft**, a **kompilátory, sestavení nástroje a moduly runtime > Podpora modulu Runtime pro nástroje pro vývoj R**.

## <a name="sql-server-integration"></a>Integrace serveru SQL Server

Systém SQL Server podporuje použití R a Python udělat pokročilou analýzu přímo v systému SQL Server. Podpora R je součástí systému SQL Server 2016 nebo novější; Python podpora je k dispozici v 2.0 CTP systému SQL Server 2017 a novějším.

Spuštěním kódu tam, kde již platný vašich dat, který nabízí řadu výhod:

- **Odstranění přesun dat**: místo přesun dat z databáze aplikace nebo modelu, můžete vytvořit R a Python aplikace v databázi. Tato funkce eliminuje překážek zabezpečení, dodržování předpisů, zásad správného řízení, integrity a hostitel podobné problémy související s přesunutím obrovské objemy dat. kolem. Také umožňuje využívat datové sady, který nelze umístit do paměti klientského počítače.

- **Snadné nasazení**: Jakmile máte R nebo Python modelu připravené, jeho nasazení do produkčního prostředí znamená, jednoduše ho vložení do skriptu T-SQL. Libovolné SQL klientské aplikace napsané v libovolném jazyce pak můžete využít výhod modely a intelligence prostřednictvím volání uložené procedury. Žádná konkrétní R nebo Python integrace jsou nezbytné.

- **Podnikové úrovni výkonu a možností škálování**: pokročilé funkce systému SQL Server můžete použít jako tabulka v paměti a ve sloupci ukládání indexy s vysokým výkonem škálovatelné rozhraní API v balíčcích RevoScaleR a RevoScalePy. Odstranění přesun dat také znamená vyhnout omezení paměti klienta, jako vaše data zvětšování nebo chcete zvýšit výkon aplikace.

- **Rozšiřitelnost bohaté**: můžete nainstalovat a spustit některé z nejnovější open source balíčky R nebo Python v systému SQL Server k vytvoření hloubkové učení a AI aplikace na velmi velké objemy dat v systému SQL Server. Instalace balíčku v systému SQL Server je jednoduché, instalaci balíčku na místním počítači.

- **Široké dostupnosti bez dalších poplatků**: R a Python integrace jsou k dispozici ve všech edicích systému SQL Server 2017 a novější, včetně edice Express. (R podpora je k dispozici v systému SQL Server 2016 a novější).

Abyste naplno využili možnosti integrace systému SQL Server, musíte taky nainstalovat **úložiště dat a zpracování** zatížení s **SQL Server Data Tools** možnost. Tato možnost umožňuje SQL IntelliSense, zvýraznění syntaxe a nasazení.

![Úlohami datového úložiště a zpracování](media/data-storage-workload.png) &nbsp;&nbsp; &nbsp;&nbsp; ![Úložiště dat a zpracování úlohy možnosti](media/data-storage-workload-options.png)

Další informace:

- [Práce s SQL serverem a R](../rtvs/sql-server.md)
- [Databáze pokročilou analýzu s R v systému SQL Server 2016](https://blogs.technet.microsoft.com/dataplatforminsider/2016/03/29/in-database-advanced-analytics-with-r-in-sql-server-2016/)
- [Python v SQL serveru 2017: rozšířeného v databázi machine learning](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/19/python-in-sql-server-2017-enhanced-in-database-machine-learning/)

## <a name="additional-services-and-sdks"></a>Další služby a sady SDK

Kromě Novinky v zatížení vědecké zpracování dat a aplikací Analytics přímo službu Azure poznámkových bloků a sady Azure SDK pro jazyk Python jsou užitečné také vědecké zpracování dat.

Sada Azure SDK pro Python usnadňuje využívat a spravovat služby Microsoft Azure z aplikací, které běží na systému Windows, Mac OSX a Linux. Další informace najdete v tématu [Azure SDK pro jazyk Python](../python/azure-sdk-for-python.md)

Azure poznámkových bloků (momentálně ve verzi preview) poskytuje bezplatné online přístup k poznámkové bloky Jupyter systémem Microsoft Azure v cloudu. Služba obsahuje ukázkové poznámkových bloků v Python, R a F # pro začátek. Navštivte[notebooks.azure.com](https://notebooks.azure.com/).

<!--Note link on the image because this one is large -->
[![Snímky obrazovky Azure notebooky se zavedením ukázce R](media/data-science-workload-notebooks.png)](media/data-science-workload-notebooks.png)