---
title: Úloha datové vědy a analytické aplikace
description: Tato úloha Visual Studio spojuje Python, F#a jejich odpovídajících runtime distribuce, včetně Anaconda. (R je také součástí sady Visual Studio 2017 pouze.)
ms.date: 02/28/2019
ms.topic: overview
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- python
- data-science
ms.openlocfilehash: dbebf486680375622e6dc313a71e82f541107fc8
ms.sourcegitcommit: 0e22ead8234b2c4467bcd0dc047b4ac5fb39b977
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59366325"
---
# <a name="install-data-science-support-in-visual-studio"></a>Nainstalovat podporu datové vědy v sadě Visual Studio

Úlohy pro datové vědy a analytické aplikace, které výběru a instalaci pomocí instalačního programu sady Visual Studio, spojuje několik jazyků a jejich odpovídajících runtime distribuce:

::: moniker range="vs-2017"
- [Python a Anaconda](../python/overview-of-python-tools-for-visual-studio.md)
- [F#s použitím rozhraní .NET framework](/dotnet/fsharp/)
- [R a Microsoft R Client](../rtvs/index.md)
::: moniker-end

::: moniker range="vs-2019"
- [Python](../python/overview-of-python-tools-for-visual-studio.md)
- [F#s použitím rozhraní .NET framework](/dotnet/fsharp/)
::: moniker-end

![Pro datové vědy a analytické aplikace funkcí v instalačním programu sady Visual Studio](media/workload/data-science-workload.png)

::: moniker range="vs-2017"
Python a jazyka R jsou dvě primární skriptovací jazyky používané pro datové vědy. Oba jazyky se snadno učí a podporují bohatý ekosystém balíčků. Tyto balíčky adres širokou škálu scénářů, jako je získání dat, čištění, model školení, nasazení a vykreslení. F#je výkonná jazyková funkcionální .NET, která je vhodná pro širokou škálu úloh zpracování dat.
::: moniker-end

::: moniker range="vs-2019"
Python je primární skriptovací jazyk používaný pro datové vědy. Python se snadno učí a je podporován bohatý ekosystém balíčků. Tyto balíčky adres širokou škálu scénářů, jako je získání dat, čištění, model školení, nasazení a vykreslení. F#je výkonná jazyková funkcionální .NET, která je vhodná pro širokou škálu úloh zpracování dat. (Pro jazyk R doporučujeme [poznámkových bloků Azure](https://notebooks.azure.com).)
::: moniker-end

<!--Note link on the image because this one is large -->
[![Snímky obrazovky sady Visual Studio s jazykem R, Python, aF#](media/workload/data-science-workload-screens.png)](media/workload/data-science-workload-screens.png#lightbox)

## <a name="workload-options"></a>Možnosti úlohy

Ve výchozím nastavení nainstaluje zatížení následující možnosti, které můžete upravit v části Souhrn pro zatížení v instalačním programu sady Visual Studio:

::: moniker range="vs-2019"
- F#Podpora klasické pracovní plochy jazyka
- Python:
  - Podpora jazyka Python
  - Podpora webů v Pythonu
::: moniker-end

::: moniker range="vs-2017"
- F#podpora jazyků
- Python:
  - Podpora jazyka Python
  - [Anaconda3, 64-bit](https://www.continuum.io), distribuce Python, která obsahuje knihovny rozsáhlé datové vědy a interpret Pythonu.
  - Podpora webů v Pythonu
  - Podpora šablon Cookiecutter
- R:
  - Podpora jazyka r.
  - Podpora modulu runtime pro vývojové nástroje R
  - [Microsoft R Client](/machine-learning-server/r-client/what-is-microsoft-r-client) (od Microsoftu plně kompatibilní, – podporované komunitou interpret R pomocí knihovny ScaleR pro rychlejší výpočty na jednotlivé uzly a clustery. Můžete také použít libovolný jazyka R z [CRAN](https://cran.r-project.org/).)
::: moniker-end

## <a name="sql-server-integration"></a>Integrace SQL Serveru

::: moniker range="vs-2017"
Systém SQL Server podporuje pomocí Pythonu a R pro pokročilé analýzy přímo v systému SQL Server. Podpora jazyka R je součástí systému SQL Server 2016 a vyšší. Podpora Pythonu je k dispozici v SQL serveru 2017 CTP 2.0 nebo novější.
::: moniker-end

::: moniker range=">=vs-2019"
SQL Server podporuje, pomocí Pythonu pro pokročilé analýzy přímo v systému SQL Server. Podpora Pythonu je k dispozici v SQL serveru 2017 CTP 2.0 nebo novější.
::: moniker-end

Díky spouštění kódu, kde již vaše data kdekoli budete moct využívat následující výhody:

- **Odstranění přesun dat**: Místo přesouvá data z databáze pro vaše aplikace nebo modelu, můžete vytvářet aplikace v databázi. Tato funkce eliminuje bariéry zabezpečení, dodržování předpisů, zásad správného řízení, integritu a celou řadu podobné problémy související s obrovských objemů dat po přesunutí. Můžete také využívat datové sady, který nelze umístit do paměti klientského počítače.

- **Snadné nasazení**: Jakmile budete mít připravený modelu, jeho nasazení do produkčního prostředí je jednoduché vkládání ve skriptu T-SQL. Všechny SQL klientské aplikace napsané v libovolném jazyce pak můžete využít výhod modely a inteligence pomocí volání uložené procedury. Žádné konkrétní jazyk integrace jsou nezbytné.

- **Výkon na podnikové úrovni a škálování**: Pokročilé funkce serveru SQL Server můžete použít jako tabulka v paměti a ve sloupci ukládat v balíčcích RevoScale indexy s rozhraními API pro vysoce výkonné škálovatelné. Úplného oproštění od přesunu dat taky znamená, že vyhnout tak klienta omezení paměti, jak roste vaše data nebo chcete zvýšit výkon aplikace.

- **Bohatá rozšiřitelnost**: Můžete nainstalovat a spustit některý z nejnovější opensourcových balíčků na SQL serveru k sestavení aplikace AI a hloubkového učení na velké objemy dat v systému SQL Server. Instalace balíčku v systému SQL Server je jednoduché, stačí instalaci balíčku na místním počítači.

- **Široký dostupnost bez dalších poplatků**: Integrace jazyka jsou k dispozici ve všech edicích systému SQL Server 2017 a novějších, včetně Express edition.

Plně využít integraci s SQL serverem, použijte k instalaci instalačního programu sady Visual Studio **ukládání a zpracování dat** úlohy **SQL Server Data Tools** možnost. Druhou možnost umožňuje SQL IntelliSense, zvýrazňování syntaxe a nasazení.

![Úloze ukládání a zpracování dat](media/workload/data-storage-workload.png) &nbsp;&nbsp;&nbsp;&nbsp; ![Úložiště dat a zpracování úloh možností](media/workload/data-storage-workload-options.png)

Další informace:

::: moniker range="vs-2017"
- [Práce s využitím SQL serveru a jazyka R](../rtvs/integrating-sql-server-with-r.md)
- [V databázi pokročilé analýzy s jazykem R v SQL serveru 2016 (blog)](https://blogs.technet.microsoft.com/dataplatforminsider/2016/03/29/in-database-advanced-analytics-with-r-in-sql-server-2016/)
::: moniker-end
- [Python v sadě SQL Server 2017: rozšířené v databázi machine learning (blog)](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/19/python-in-sql-server-2017-enhanced-in-database-machine-learning/)

## <a name="additional-services-and-sdks"></a>Další služby a sady SDK

Kromě přímo Novinky v úloze datové vědy a analytické aplikace služby Azure poznámkových bloků a sady Azure SDK for Python jsou také užitečná pro datové vědy.

Sada Azure SDK pro Python umožňuje snadno využívat a spravovat služby Microsoft Azure z aplikací běžících ve Windows, Mac a Linux. Další informace najdete v tématu [sady Azure SDK pro Python](../python/azure-sdk-for-python.md)

Azure poznámkových bloků (aktuálně ve verzi preview) poskytuje Bezplatná online přístup k poznámkové bloky Jupyter, které běží v cloudu v Microsoft Azure. Součástí služby je v jazyce Python, R a ukázkové poznámkové bloky a F# vám pomůžou začít. Navštivte [notebooks.azure.com](https://notebooks.azure.com/).

<!--Note link on the image because this one is large -->
[![Snímky obrazovky z Azure poznámkové bloky s Úvod do ukázkové R](media/workload/data-science-workload-notebooks.png)](media/workload/data-science-workload-notebooks.png#lightbox)
