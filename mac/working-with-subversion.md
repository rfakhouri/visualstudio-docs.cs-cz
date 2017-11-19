---
title: "Práce s Subversion | Microsoft Docs"
description: "Pomocí Subversion v sadě Visual Studio for Mac."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 2400ED9C-6236-4C0A-A3AB-9D7CBE1F0CF4
ms.openlocfilehash: 026e3625b4ee2d6582ce5539e5cab68c945f09c0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="working-with-subversion"></a>Práce s Subversion

Jak je uvedeno výše v tomto článku, Subversion je systém správy centralizované verzí, která umožňuje podívejte se na jednu hlavní kopii centralizované data. Na rozdíl od Git se odhlašuje Subversion úložiště není klonovat úložiště v celé, pouze pořídí snímek v tomto bodě v čase.

Subversion používá model kopie upravit sloučení aby uživatelé mohli pracovat na stejného úložiště najednou. To znamená, že každý uživatel vytvoří kopii centralizované data, která na mohou pak pracovat nezávisle místní nebo funkční. Změny uživatelů, kteří pracují kopie jsou sloučeny chronologickém způsobem.

Představte si například, že uživatel A a B uživatele projděte si kopii ze vzdáleného úložiště a každý upravit soubory. Uživatel A dokončení změny a je vzdáleně potvrdí. Předtím, než uživatel B provede práci, budou muset aktualizovat změnami od vzdálených, a tím Probíhá slučování v změny uživatele A jejich pracovní kopie.

V této části se podíváme na tom, jak lze použít Subversion pro správu verzí v sadě Visual Studio for Mac.

Následující obrázek ukazuje možnosti poskytované Visual Studio pro Mac položku nabídky verzí:

![Položky nabídky verze ovládacího prvku](media/version-control-svnVersionControlMenu.png)

V níže uvedených částech se popisují jednotlivé možnosti podrobněji.

## <a name="checkout"></a>Najdete v článku věnovaném...

Před zahájením používání vzdáleného úložiště Subversion, musíte rezervovat úložišti vytvořit kopii tento adresář místní, nebo při práci, na místním počítači.

Informace o použití **najdete v článku věnovaném** funkce v sadě Visual Studio pro Mac, postupujte podle kroků v [nastavení úložiště Subversion](~/set-up-subversion-repository.md) části.

## <a name="update-solution"></a>Aktualizace řešení

Při použití vzdáleného úložiště, je důležité si pamatovat, jiných uživatelů může být změny souborů, provedení pracovní kopii zastaralá. V očekávání to vždy doporučujeme před zahájením práce a před provedením načítat všechny změny z úložiště do vašeho řešení. Chcete-li to provést, vyberte *verzí > řešení aktualizací* položku nabídky.

## <a name="review-solution-and-commit"></a>Zkontrolujte řešení a potvrzení

Ke zkontrolování změn v souborech, použijte změny, viny, protokol a slučování karty na každý dokument, jak je uvedeno dále:

![Verze ovládací prvek karty](media/version-control-vcTabs.png)

Zkontrolujte všechny změny v projektu procházením **verzí > zkontrolujte řešení a potvrzení** položky nabídky:

![Přečtěte si řešení](media/version-control-vcStatus.png)

To umožňuje zobrazení všech změn do každého souboru projektu s možností vrátit, vytvořit oprava nebo potvrzení.

Potvrdit souboru do vzdáleného úložiště, stiskněte klávesu potvrzení..., zadejte zprávu potvrzení a potvrďte pomocí tlačítka potvrzení:


![Potvrzení soubor](media/version-control-svnCommit.png)

Tím se pošle změny do úložiště, kde se vytvořit novou revizi všechny změny.
