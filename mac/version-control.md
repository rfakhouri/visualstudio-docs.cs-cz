---
title: "Správa verzí | Microsoft Docs"
description: "Pomocí Git a Subversion v sadě Visual Studio for Mac."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 49917483-28AA-4598-A847-71F1F2E0DCB5
ms.openlocfilehash: 6e467cf6acda75948a189309b7648b1c4c085941
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="version-control"></a>Správa verzí

Správa verzí je systém pro správu přes mnoho různých verzí souborů a - v softwaru vývoj - je obecně přispěli k celá řada vývojářů. Hlavní účel žádné systém správy verzí (_VC_) je nalezení řešení, které umožňuje všem uživatelům pracovat na základu kódu ve stejnou dobu.

Základem všech verzí systému je _úložiště_, který pracuje jako centrální data ukládat všechny různé soubory – podobně jako souborový server. Na rozdíl od souborový server, ale úložiště obsahuje celou historii projekt a všechny revize, které byly provedeny.

Pokud úložiště je centrální datové úložiště, je logický pro každého uživatele tak, aby měl místního úložiště dat, což jim umožní na něm pracovat. Tento postup se nazývá _pracovní kopie_. V sadě Visual Studio pro Mac pracovní kopie se zobrazí stejně jako ostatní místního adresáře na počítači což umožňuje číst z a zapisovat do žádné soubory. Ale protože Visual Studio pro Mac má integraci systému správy verzí, můžete využít power Subversion a Git bez opuštění prostředí IDE.

Subversion je systém správy centralizované verzí. To znamená, že je jeden server, který obsahuje všechny soubory a revize, ze kterých uživatelé sjednotit, zkontrolujte verzi všechny soubory. Pokud jsou soubory rezervovány ze vzdáleného úložiště Subversion, uživatel dostane snímek úložiště v tomto bodě v čase.

Git je distribuovaný systém správy verzí umožňující týmy pro práci na stejné dokumenty současně. To znamená, že existuje, může jeden server, který obsahuje všechny soubory, ale vždy, když úložiště je rezervována z tohoto centrální zdroje, úložišti celý místně naklonována k vašemu počítači.

# <a name="basic-concepts"></a>Základní koncepty 

Visual Studio pro Mac poskytuje podporu pro systémy řízení verzí Git a podverze. Příručky vedou následující odkazy prozkoumejte nastavení úložiště Git a Subversion pomocí sady Visual Studio pro Mac, a také jednoduché funkce, jako je kontrola, potvrzení a předání změny.

* [Nastavení úložiště Git](~/set-up-git-repository.md) 
* [Práce s Gitem](~/working-with-git.md)
* [Nastavení úložiště Subversion](~/set-up-subversion-repository.md)
* [Práce s Subversion](~/working-with-subversion.md)