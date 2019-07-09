---
title: Práce s úložištěm Subversion
description: Pomocí dílčích verzí v sadě Visual Studio pro Mac.
author: jmatthiesen
ms.author: jomatthi
ms.date: 05/06/2018
ms.assetid: 2400ED9C-6236-4C0A-A3AB-9D7CBE1F0CF4
ms.openlocfilehash: d687215bc91dc01a284c49c141a6e52a16ce9e7a
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2019
ms.locfileid: "67692142"
---
# <a name="working-with-subversion"></a>Práce s úložištěm Subversion

Subversion je centralizovaný systém správy verzí, která umožňuje podívejte se na jeden hlavní kopii centralizovaného data. Na rozdíl od Git a rezervaci úložiště Subversion není klonovat celé úložiště, jenom pořídí snímek v daném okamžiku v čase.

Dílčí verze používá model kopírování upravit sloučení pro umožňují uživatelům pracovat současně na stejném úložišti. To znamená, že každý uživatel vytvoří kopii centralizovaného data, která pracují nezávisle na místní, nebo při práci. Změny uživatelů pracovní kopie jsou sloučeny chronologickém způsobem.

Představte si například, že uživatel A a B uživatele rezervovat kopírování ze vzdáleného úložiště a jejich jednotlivých souborů změnit. Uživatel A dokončí úpravy a potvrdí vzdáleně. Předtím, než uživatel B provádí svou práci, musí aktualizovat změny ze vzdáleného počítače, sloučení v změny uživatele A jejich pracovní kopie.

Následující části prozkoumat, jak Subversion lze pro správu verzí v sadě Visual Studio pro Mac.

Následující obrázek ukazuje možnosti poskytovaný sadou Visual Studio for Mac pomocí položky nabídky správy verzí:

![Položky nabídky ovládací prvek verze](media/version-control-svnVersionControlMenu.png)

## <a name="checkout"></a>Rezervace...

Před zahájením používání vzdáleného úložiště Subversion, projděte si úložiště k vytvoření pracovní kopii tohoto adresáře na místním počítači.

Najdete informace o použití **Checkout** funkcí v sadě Visual Studio pro Mac, postupujte podle kroků v [nastavení úložiště Subversion](set-up-subversion-repository.md) oddílu.

## <a name="update-solution"></a>Aktualizace řešení

Při použití vzdáleného úložiště, je dobré si uvědomit, že ostatním uživatelům může být změny souborů, provádění vaše pracovní kopie zastaralé. Čekat na případná je v konfliktu vždy doporučujeme před zahájením práce a před potvrzením načítat všechny změny z úložiště do vašeho řešení. Chcete-li vložit změny, vyberte **verzí > řešení Update** položky nabídky.

## <a name="review-solution-and-commit"></a>Kontrola řešení a odeslat

Ke zkontrolování změn v souborech, použijte změny, viny, protokol a sloučit kartách na jednotlivých dokumentů, jak je znázorněno na následujícím obrázku:

![Verze ovládacího prvku karty](media/version-control-vcTabs.png)

Zkontrolujte všechny změny v projektu tak, že přejdete **verzí > řešení zkontrolujte a potvrďte změny** položky nabídky:

![Kontrola řešení](media/version-control-vcStatus.png)

To umožňuje zobrazení všech změn v každém souboru projektu s možností vrácení, vytvořit opravu, nebo potvrzení.

Zapsat do souboru do vzdáleného úložiště, stiskněte klávesu potvrzení..., zadejte zprávu potvrzení, a potvrďte tlačítkem potvrzení:

![Potvrzují se soubor](media/version-control-svnCommit.png)

Tento tok odešle změny do úložiště, které vytvářejí Nová revize všechny provedené změny.

## <a name="see-also"></a>Viz také:

- [Nastavení úložiště Subversion](set-up-subversion-repository.md)
