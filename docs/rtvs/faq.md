---
title: "R Tools pro Visual Studio – nejčastější dotazy | Microsoft Docs"
ms.custom: 
ms.date: 11/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e656ac64-915a-40bb-8196-93d33250ef98
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 79420e09f7ca0b01ce97fc19a063a8b15431b544
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="frequently-asked-questions"></a>Nejčastější dotazy

## <a name="visual-studio-support"></a>Visual Studio – podpora

**OTÁZKY. Funguje RTVS v OS X nebo Linux?**

A. RTVS je v současné době postavená na Visual Studio, který je pouze pro systém Windows implementace. Společnost Microsoft pracuje na odstranění příčin podporu na Visual Studio Code a Visual Studio for Mac. Odkazovat na [RTVS vydání #1295](https://github.com/Microsoft/RTVS/issues/1295).

**OTÁZKY. Funguje s edice sady Visual Studio Express RTVS?**

A. Ne.

**OTÁZKY. Můžete použít rozšíření sady Visual Studio s RTVS?**

A. Absolutně. Ve skutečnosti tady jsou některé, které jsou pro lidí pracujících s R.

- [VsVim pro vim vazeb klíče](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)
- [Github](https://marketplace.visualstudio.com/items?itemName=GitHub.GitHubExtensionforVisualStudio)
- [Editor markdownu s živém náhledu](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.MarkdownEditor)

Najdete v článku [Visual Studio Marketplace](https://marketplace.visualstudio.com/) najít další.

**OTÁZKY. Protože RTVS je v sadě Visual Studio, to znamená, že R můžete snadno použít s C#, C++ a dalších jazyků Microsoft?**

A. Ne. RTVS je nástroj pro vývoj kódu jazyka R a používá standardní nativní R překladače. Interoperabilita mezi R a dalších jazyků není aktuálně podporován.

**OTÁZKY. Funguje s neanglické národní prostředí RTVS?**

A. Je 1.0 verzi RTVS pouze angličtina. Verze 1.1 bude lokalizované pro stejnou skupinu jazyků, které je v sadě Visual Studio, sám sebe. Do té doby, použijte [anglické jazykové sady pro Visual Studio 2015](https://www.microsoft.com/download/details.aspx?id=48157), nebo v aplikaci Visual Studio 2017, spusťte instalační program a vyberte v angličtině **jazykové sady** kartě.

![Mezinárodní nastavení pro Visual Studio 2017](media/FAQ-international-settings.png)

**OTÁZKY. Opravdu líbí se aktuální nastavení sady Visual Studio, ale chcete vyzkoušet nové vědecké zpracování dat nastavení. Co mám dělat?**

A. Uložit aktuální nastavení sady Visual Studio pomocí **nástroje > Import a Export nastavení...** , potom přepnout na vědecké zpracování dat nastavení. Chcete-li obnovit uložená nastavení, použijte **nastavení importu a exportu...**  příkaz znovu.

**OTÁZKY. Můžete uložit Moje projektu sady Visual Studio ve sdílené síťové složce?**

A. Ne, Visual Studio nepodporuje projekty načítání v síťové sdílené složce.

## <a name="r-interpretersintegration"></a>R překladače/integrace

**OTÁZKY. Jaké překladače R RTVS funguje s?**

A. [CRAN r.](https://cran.r-project.org/), [klienta Microsoft R a Microsoft Machine Learning serveru](/machine-learning-server/)

**OTÁZKY. Kde lze stáhnout tyto překladače?**

A. V tématu [instalace](installation.md).

Q **co je Microsoft R Server?**

A. R Server je starší název [Microsoft Machine Learning Server](/machine-learning-server/what-is-machine-learning-server).

**OTÁZKY. Funguje s 32-bit Edition R RTVS?**

A. Ne, RTVS podporuje pouze 64-bit Edition R spuštěné v 64bitových edicích systému Windows.

**OTÁZKY. Funguje RTVS s Moje správy zdrojového kódu?**

A. Ano, můžete použít systému správy zdrojů, který je integrován do sady Visual Studio.

**OTÁZKY. Jaké jsou doporučené `.gitignore` nastavení pro projekt RTVS?**

A. Github udržuje hlavní úložiště doporučené `.gitignore` soubory. Zobrazí se zde: [R .gitignore](https://github.com/github/gitignore/blob/master/R.gitignore)

## <a name="remote-services"></a>Vzdálené

OTÁZKY. **Novinky vzdálené v sadě Visual Studio**

A. Vzdálené R pro sadu Visual Studio můžete nastavit počítač systému Windows nebo Linux a potom se připojte k němu z RTVS. V tématu [nastavení vzdálené pracovní prostory](workspaces-remote-setup.md).

OTÁZKY. **Můžete RTVS připojit k serveru R Microsoft?**

A. Ne, protože Microsoft R Server je různé technologie a neposkytuje mechanismus stejné připojení jako vyžadují RTVS.

OTÁZKY. **Můžete RTVS připojit k virtuálnímu počítači vytvořené pomocí image virtuálního počítače vědecké účely dat v Azure?**

A. Ano; předinstalovaný image virtuálního počítače vědecké účely dat pomocí služby vzdálené R pro sadu Visual Studio.

Q, **RTVS můžete připojit ke vzdálenému počítači s R nainstalované?**

Ke spouštění kódu vytvořeného R ve vzdáleném počítači musí být některé služby naslouchání na požadavky, kód příjem a odesílání výsledky zpět na klientský počítač. Je provést vzdálené R pro sadu Visual Studio. V tématu [nastavení vzdálené pracovní prostory](workspaces-remote-setup.md).

OTÁZKY. **Co je Vzdálená relace?**

A. Najdete v článku [spustit na vzdáleném serveru](/machine-learning-server/r/how-to-execute-code-remotely) v dokumentaci k serveru Machine Learning.

## <a name="rtvs-development-and-features"></a>Vývoj RTVS a funkce

**OTÁZKY. Funkce X chybí, ale je Rstudia!**

A. Rstudia je, protože přitahují a vyspělá IDE pro R, která jsou ve vývoji mnoha let. RTVS požádá o kritických funkcích, které budete muset být úspěšné. Pomáhají určit priority budoucí pracovní provedením [RTVS průzkum](https://www.surveymonkey.com/r/RTVS1) a souborů problémy na [Githubu](https://github.com/Microsoft/RTVS/issues/).

**OTÁZKY. Může I přispívat k RTVS?**

A. Samozřejmě. Zdrojový kód je umístěn [Githubu](https://github.com/microsoft/RTVS). Pomocí nástroje Sledování problém odeslání chyb spolu a komentář k těch, které již selhala.

Budete také můžete přispívat do této dokumentace&mdash;právě vyberte **upravit** v pravém horním rohu stránky jakoukoli stránku. Komentáře k dokumentaci jsou také úvodní, které můžete přidat v dolní části jakoukoli stránku.
