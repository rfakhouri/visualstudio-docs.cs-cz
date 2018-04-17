---
title: Zobrazit paměti pro proměnné v ladicím programu | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.memory
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Memory window
- strings [Visual Studio], viewing
- debugger [Visual Studio], Memory window
- memory [Visual Studio], debugging
- debugging [Visual Studio], Memory window
- buffers, viewing
ms.assetid: 7f7a0439-10e4-4966-bb2d-51f04cda4fe2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e5e2c43f48a1a91c35c770f5f7150972bebb1a1a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="use-the-memory-windows-in-the-visual-studio-debugger"></a>Použití Windows paměti v ladicím programu sady Visual Studio
**Paměti** okno poskytuje pohled na místo na paměti, které používá vaše aplikace. **Sledovat** okně **QuickWatch** dialogové okno, **automobily** okně a **místní hodnoty –** okno zobrazit, obsah proměnné, které jsou uložené na konkrétní umístění v paměti. Ale **paměti** v okně se zobrazí ve velkém měřítku obrázek. Toto zobrazení může být vhodné pro zkoumání velké částí data (vyrovnávací paměti nebo velké řetězce, např.), která nezobrazovat i v dalších oknech. Ale **paměti** není omezena na zobrazení dat okno. Se zobrazuje všechno, co v paměti, informaci, jestli obsah data, kódu nebo náhodné bitů paměti v nepřiřazené paměti.  
  
 **Paměti** okno je k dispozici pouze v případě, že je povoleno ladění úrovni adresu v **možnosti** dialogové okno, **ladění** uzlu. **Paměti** okno není k dispozici pro skript nebo SQL, které jsou jazyky, které nelze rozpoznat koncept paměti.  
  
## <a name="opening-a-memory-window"></a>Otevřete okno paměti  
  
#### <a name="to-open-a-memory-window"></a>K otevření okna paměti  
  
1.  Spusťte ladění, pokud jste ještě nejsou v režimu ladění.  
  
2.  V **ladění** nabídky, přejděte na příkaz **Windows**. Potom přejděte na **paměti** a pak klikněte na **paměti 1**, **paměti 2**, **paměti 3**, nebo **paměti 4**. (Nižší úrovně edicích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pouze jedinou **paměti** okno. Pokud použijete jednu z těchto edicích, stačí kliknout na **paměti**.)  
  
## <a name="paging-in-the-memory-window"></a>Stránkování v okně paměti  
 **Paměti** okna je svislý posuvník, který pracuje nestandardní způsobem. Adresní prostor moderní počítače je velmi velké a můžete snadno může získat ztrátě metodou úchytu posuvníku a jeho přetažením na náhodném umístění. Z tohoto důvodu úchytu je "pružinou" a vždy zůstává ve středu posuvník. V nativním kódu aplikace mohou stránku nahoru nebo dolů ale nejde o volně přejděte.  
  
 Vyšší adresy paměti se zobrazí v dolní části okna. Chcete-li zobrazit adresu vyšší, posuňte se dolů, není až.  
  
#### <a name="to-page-up-or-down-in-memory"></a>Na stránce nahoru nebo dolů v paměti  
  
1.  Na stránku dolů (přesunout vyšší adresa paměti), klikněte v části úchytu v svislý posuvník.  
  
2.  Na stránce nahoru (přesunout nižší adresa paměti), klikněte výše úchytu svislý posuvník.  
  
## <a name="selecting-a-memory-location"></a>Výběr umístění v paměti  
 Pokud chcete přesunout do vybraného umístění v paměti okamžitě, můžete tak učinit pomocí operace přetažení myší nebo změnou hodnoty v **adresu** pole. **Adresu** pole lze zadat pouze číselné hodnoty, ale také výrazů, která se vyhodnotí jako adresy. Ve výchozím nastavení **paměti** okno zpracovává **adresu** výraz jako výraz za provozu, který je znovu vyhodnocena jako váš program spustí. Výrazy za provozu může být velmi užitečné. Například je můžete použít k zobrazení paměti, která je dotýkal podle ukazatel.  
  
#### <a name="to-select-a-memory-location-by-dragging-and-dropping"></a>Vyberte umístění v paměti pomocí přetahování a vkládání  
  
1.  V jakémkoli okně vyberte paměti adresu nebo ukazatel proměnné, která obsahuje adresu paměti.  
  
2.  Přetáhněte adresy nebo ukazatel **paměti** okno.  
  
#### <a name="to-select-a-memory-location-by-editing"></a>Vyberte umístění v paměti úpravou  
  
1.  V **paměti** vyberte **adresu** pole.  
  
2.  Zadejte nebo vložte adresu, kterou chcete zobrazit a potom stiskněte klávesu **ENTER**.  
  
## <a name="changing-the-way-the-memory-window-displays-information"></a>Mění způsob informace zobrazí okno paměti  
 Můžete upravit způsob **paměti** v okně se zobrazí obsah paměti. Ve výchozím nastavení obsah paměti se zobrazí jako celá čísla jeden bajtů v šestnáctkovém formátu a počet sloupců je určena automaticky aktuální šířkou okna.  
  
#### <a name="to-change-the-format-of-the-memory-contents"></a>Chcete-li změnit formát obsah paměti  
  
1.  Klikněte pravým tlačítkem myši **paměti** okno.  
  
2.  Vyberte formát, který chcete.  
  
#### <a name="to-change-the-number-of-columns-in-the-memory-window"></a>Chcete-li změnit počet sloupců v okně paměti  
  
1.  Na panelu nástrojů v horní části **paměti** okno, vyhledejte **sloupce** seznamu.  
  
2.  V **sloupce** vyberte počet sloupců, které chcete zobrazit nebo vybrat **automaticky** pro automatickou úpravu podle šířky okna.  
  
 Pokud nechcete, aby obsah **paměti** okna je možné změnit jako aplikaci spustí, můžete vypnout vyhodnocení výrazu za provozu.  
  
#### <a name="to-toggle-live-evaluation"></a>K přepnutí za provozu vyhodnocení  
  
1.  Klikněte pravým tlačítkem myši **paměti** okno.  
  
2.  V místní nabídce klikněte na tlačítko **přehodnocovat automaticky**.  
  
     Pokud za provozu vyhodnocení na, bude vybrána možnost a kliknutím ji vypne za provozu vyhodnocení. Pokud vyhodnocení za provozu je vypnutý, není vybrána možnost a kliknutím na tlačítko se zapne za provozu vyhodnocení.  
  
 Můžete skrytí nebo zobrazení panelu nástrojů v horní části **paměti** okno. Nebudete mít přístup k řešení pole nebo jiné nástroje, dokud je skrytý panelu nástrojů.  
  
#### <a name="to-toggle-the-toolbar"></a>K přepnutí panelu nástrojů  
  
1.  Klikněte pravým tlačítkem myši **paměti** okno.  
  
2.  V místní nabídce klikněte na tlačítko **zobrazit panel nástrojů**.  
  
     Panelu nástrojů zobrazí nebo zmizí, v závislosti na jeho předchozího stavu.  
  
## <a name="following-a-pointer-through-memory"></a>Následující ukazatele prostřednictvím paměti  
 V nativním kódu aplikace můžete zaregistrovat názvy jako živé výrazy. Například můžete ukazatel zásobníku podle zásobníku.  
  
#### <a name="to-follow-a-pointer-through-memory"></a>Podle ukazatel prostřednictvím paměti  
  
1.  V **paměti** okno **adresu** zadejte výraz ukazatele. Proměnné ukazatele musí být v aktuálním oboru. V závislosti na jazyk bude pravděpodobně nutné dereference ho.  
  
2.  Stiskněte klávesu **ENTER**.  
  
     Teď, když použijete příkaz provádění, jako **krok**, adresa paměti, který se zobrazí automaticky změní jako ukazatel změny.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)