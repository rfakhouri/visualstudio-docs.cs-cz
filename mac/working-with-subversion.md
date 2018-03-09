---
title: "Práce s Subversion | Microsoft Docs"
description: "Pomocí Subversion v sadě Visual Studio for Mac."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 2400ED9C-6236-4C0A-A3AB-9D7CBE1F0CF4
ms.openlocfilehash: 39f7407854b2ff74552209762565236adb403d84
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="working-with-subversion"></a>Práce s Subversion

Subversion je systém správy centralizované verzí, která umožňuje podívejte se na jednu hlavní kopii centralizované data. Na rozdíl od Git se odhlašuje Subversion úložiště není klonovat úložiště v celé, pouze pořídí snímek v tomto bodě v čase.

Subversion používá model kopie upravit sloučení aby uživatelé mohli pracovat na stejného úložiště najednou. To znamená, že každý uživatel vytvoří kopii centralizované data, která pracují nezávisle na místní nebo funkční. Změny uživatelů, kteří pracují kopie jsou sloučeny chronologickém způsobem.

Představte si například, že uživatel A a B uživatele projděte si kopii ze vzdáleného úložiště a každý upravit soubory. Uživatel A dokončení změny a je vzdáleně potvrdí. Předtím, než uživatel B provede práci, musí se změnami od vzdálených, Probíhá slučování v změny uživatele A aktualizovat jejich pracovní kopie.

V následujících částech prozkoumat Subversion použití pro správu verzí v sadě Visual Studio for Mac.

Následující obrázek ukazuje možnosti poskytované Visual Studio pro Mac položku nabídky verzí:

![Položky nabídky verze ovládacího prvku](media/version-control-svnVersionControlMenu.png)

## <a name="checkout"></a>Najdete v článku věnovaném...

Před zahájením používání vzdáleného úložiště Subversion, projděte si úložišti vytvořit kopii pracovní tento adresář na místním počítači.

Informace o použití **najdete v článku věnovaném** funkce v sadě Visual Studio pro Mac, postupujte podle kroků v [nastavení úložiště Subversion](~/set-up-subversion-repository.md) části.

## <a name="update-solution"></a>Aktualizace řešení

Při použití vzdáleného úložiště, je důležité si pamatovat, jiných uživatelů může být změny souborů, provedení pracovní kopii zastaralá. Očekávaly je v konfliktu se vždy doporučuje načítat všechny změny z úložiště do řešení před zahájením práce a před potvrzením. Vyžádání změny, vyberte **verzí > řešení aktualizací** položku nabídky.

## <a name="review-solution-and-commit"></a>Zkontrolujte řešení a potvrzení

Ke zkontrolování změn v souborech, použijte změny, viny, protokol a slučování karty na každý dokument, jak je znázorněno na následujícím obrázku:

![Verze ovládací prvek karty](media/version-control-vcTabs.png)

Zkontrolujte všechny změny v projektu procházením **verzí > zkontrolujte řešení a potvrzení** položky nabídky:

![Přečtěte si řešení](media/version-control-vcStatus.png)

To umožňuje zobrazení všech změn do každého souboru projektu s možností vrátit, vytvořit oprava nebo potvrzení.

Potvrdit souboru do vzdáleného úložiště, stiskněte klávesu potvrzení..., zadejte zprávu potvrzení a potvrďte pomocí tlačítka potvrzení:


![Potvrzení soubor](media/version-control-svnCommit.png)

Tím se pošle změny do úložiště, kde se vytvořit novou revizi všechny změny.
