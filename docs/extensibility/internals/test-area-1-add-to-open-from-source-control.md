---
title: 'Testovací oblast 1: Přidání nebo otevření ze správy zdrojových kódů | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], adding and opening solutions
- source control plug-ins, adding and opening solutions
ms.assetid: 5b3b5b08-5e9b-41be-ac72-c63957faed22
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2ba64bdcf299f52d0200e1fa66dead11a8824c14
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63429989"
---
# <a name="test-area-1-add-toopen-from-source-control"></a>Testovací oblast 1: Přidat / otevřít ze správy zdrojového kódu
Tento zdroj – ovládací prvek modulu plug-in testu pozadí oblasti uvedení řešení nebo projektů pod správou zdrojových kódů a načítání ze správy zdrojového kódu.

## <a name="command-menu-access"></a>Přístup do příkazu nabídky
 Následující [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí nabídky cesty se používají v testovacích případů:

- Pro [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)], otevřít ze správy zdrojového kódu: **Soubor**, **otevřít**, **projektu**/**řešení**; hledejte v [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)] umístění.

- Pro další ovládací prvek moduly plug-in zdrojového kódu otevřete ze správy zdrojového kódu: **Soubor**, **správy zdrojového kódu**, **otevřít ze správy zdrojových kódů**.

- Přidáte do správy zdrojového kódu: **Soubor**, **správy zdrojového kódu**, **přidat řešení do soubor správy zdrojového kódu**, **správy zdrojového kódu**, **přidat do správy zdrojových kódůvybranýchprojektů**.

- Místní nabídky (projekt nebo řešení), **přidat řešení do správy zdrojových kódů**.

- Přidáte ze správy zdrojového kódu: **Soubor**, **správy zdrojového kódu**, **přidat projekt ze správy zdrojových kódů**.

- Pro [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)], přidejte ze zdrojového ovládacího prvku je k dispozici také z **souboru**, **přidat**, **existující projekt**; hledejte v [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)] umístění.

  > [!NOTE]
  > Cestu k místnímu souboru nebo místní služby IIS (web server) je možné v tomto testu.

## <a name="expected-behavior"></a>Očekávané chování

- Pro každý typ podporovaný projektu by měl uživatel možné "Přidat" a "Otevřít v" správy zdrojového kódu.

- Při přidání projektu do správy zdrojových kódů, odpovídající \< *ProjectName*> se vytvoří soubor .vspscc (informačního souboru projektu). Obsahuje informace o připojení a seznam souborech vyloučení. Neodstraňujte tento soubor, protože obsahuje informace specifické pro projekt.

- Při přidání řešení do správy zdrojových kódů, odpovídající \< *SolutionName*> se vytvoří soubor .vssscc (triple S). Textový soubor obsahuje informace o připojení a soubor seznamu vyloučení, podobně jako do informačního souboru projektu. Tento soubor je dočasný a existuje pouze v databázi správy zdrojových kódů.

- Při otevření řešení ze správy zdrojového kódu \< *SolutionName*> soubor .vsscc (double S), která existuje pouze v databázi správy zdrojových kódů, je vytvořeno místně do dočasného souboru. Tento soubor obsahuje cestu ze složky řešení připojení do souboru řešení. Tento soubor je dočasný a místní kopie se odstraní po dokončení operace "Otevřít ze správy zdrojového kódu".

- Po přidání projektu do správy zdrojového kódu můžete provádět všechny akce správy zdrojů na něm (prohlédněte si Get a tak dále).

## <a name="test-cases"></a>Testovací případy
 Tady jsou konkrétní testovací případy pro přidání / otevřít ze správy zdrojových kódů testovací oblast.

### <a name="case-1a-add-solution-to-source-control"></a>Případu 1a: Přidat řešení do správy zdrojového kódu
 Tento testovací případ se zaměřuje na přidání řešení do správy zdrojového kódu.

|Akce|Testovací kroky|Chcete-li ověřit očekávané výsledky|
|------------|----------------|--------------------------------|
|Přidat řešení obsahující klientský projekt do správy zdrojového kódu|1.  Vytvoření projektu klienta.<br />2.  Přidat řešení do správy zdrojového kódu (**souboru**, **správy zdrojových kódů**, **přidat řešení do správy zdrojových kódů**).|Řešení nebo projektu byl přidán do správy zdrojového kódu.|
|Přidat řešení obsahující systému souborů nebo místní služby IIS webového projektu do správy zdrojového kódu|1.  Vytvořte místní projekt webové služby IIS nebo systému souborů (pomocí tlačítka Procházet tak, aby odkazoval na umístění projektu; cesta Určuje, jaký typ webového projektu je vytvořen).<br />2.  Přidat řešení do správy zdrojového kódu (**souboru**, **správy zdrojových kódů**, **přidat řešení do správy zdrojových kódů**).|Řešení nebo projektu byl přidán do správy zdrojového kódu.|
|Přidat řešení obsahující vzdálené lokality webového projektu do správy zdrojového kódu|1.  Vytvořte projekt vzdáleného webového serveru.<br />2.  Přidat řešení do správy zdrojového kódu (**souboru**, **správy zdrojových kódů**, **přidat řešení do správy zdrojových kódů**).<br />3.  Klikněte na tlačítko **OK** v dialogovém okně upozornění přístup FrontPage.|Řešení byl přidán do správy zdrojového kódu.<br /><br /> Projekt vzdálené lokality není pod správou zdrojových kódů. (Projekty vzdálené lokality musí být řízený z vlastní server služby IIS.)|
|Přidání řešení jednoho projektu do zdrojového ovládacího prvku pomocí **přidat vybrané projekty do správy zdrojových kódů**.|1.  Vytvoření řešení jednoho projektu.<br />2.  Přidat jenom řešení do správy zdrojového kódu jako výběr (**souboru**, **správy zdrojových kódů**, **přidat vybrané projekty do správy zdrojových kódů**). Pokud tento krok úspěšný, pokračujte dalším krokem.<br />3.  Přidat projekt do správy zdrojového kódu jako výběr (**souboru**, **správy zdrojových kódů**, **přidat vybrané projekty do správy zdrojových kódů**).<br />4.  Klikněte na tlačítko **Ano** přidat projekt do stejného umístění.<br />5.  Klikněte na tlačítko **rezervovat** v **zkontrolujte navýšení kapacity pro úpravy** dialogové okno.|`Result from Step 2:`<br /><br /> Projekt a všechny soubory v projektu mají rezervovaný si zdrojový ovládací prvek indikátor a zobrazí "není pod správou zdrojových kódů".<br /><br /> `Result from Step 5:`<br /><br /> Soubor projektu a řešení jsou ve stejné složce ve správě zdrojového kódu.|
|Zrušit přidávání řešení do správy zdrojového kódu|1.  Vytvoření řešení jednoho projektu.<br />2.  Pokus o přidání projektu a řešení do správy zdrojového kódu. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />3.  Zrušte, jakmile se v systému správy zdrojového kódu.|`Result from Step 2:`<br /><br /> Dialogové okno sady zdroj umístění projektu ovládacího prvku se vyskytuje jenom jednou.<br /><br /> `Result from Step 3:`<br /><br /> Projektu přidat zrušené, projekt nebo řešení není pod správou zdrojových kódů a všechny přidat do zdrojového ovládacího prvku nabídky stále k dispozici.|

### <a name="case-1b-open-solution-from-source-control"></a>1b případu. Otevřít řešení ze správy zdrojového kódu
 Tento testovací případ se zaměřuje na otevírání řešení ze správy zdrojového kódu.

|Akce|Testovací kroky|Chcete-li ověřit očekávané výsledky|
|------------|----------------|--------------------------------|
|Otevřete řešení obsahující klientský projekt ze správy zdrojového kódu|1.  Vytvoření projektu klienta.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Zavřete řešení.<br />4.  Otevřete řešení ze správy zdrojového kódu do nového umístění.|Řešení/projekt otevřít ze správy zdrojového kódu.|
|Otevřete řešení obsahující místní nebo IIS webového projektu ze správy zdrojového kódu|1.  Vytvoření místní nebo projektu webové služby IIS.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Zavřete řešení.<br />4.  Otevřete řešení ze správy zdrojového kódu do nového umístění.|Řešení/projekt otevřít ze správy zdrojového kódu.|
|Otevřete řešení obsahující vzdálené lokality webového projektu ze správy zdrojového kódu|1.  Vytvořte projekt vzdáleného webového serveru.<br />2.  Přidáte řešení do správy zdrojového kódu. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />3.  Zavřete řešení.<br />4.  Otevřete řešení ze správy zdrojového kódu do nového umístění.|`Result from Step 2:`<br /><br /> Vzdálený webový server není pod správou zdrojových kódů.<br /><br /> `Result from Step 4:`<br /><br /> Otevřít řešení ze správy zdrojového kódu.<br /><br /> Načtení projektu vzdálené lokality, ale není pod správou zdrojových kódů.|

### <a name="case-1c-add-solution-from-source-control"></a>Případ 1c: Přidat řešení ze správy zdrojového kódu
 Tento testovací případ se zaměřuje na přidání řešení ze správy zdrojového kódu.

|Akce|Testovací kroky|Chcete-li ověřit očekávané výsledky|
|------------|----------------|--------------------------------|
|Přidejte do prázdného řešení – jednoho projektu řešení|1.  Vytvoření řešení jednoho projektu.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Zavřete řešení.<br />4.  Vytvoření druhého prázdné řešení.<br />5.  Přidat dříve řízené řešení ze správy zdrojových kódů (**souboru**, **správy zdrojových kódů**, **přidat projekt ze správy zdrojových kódů**).|Přidání projektu se zobrazí v **Průzkumníka řešení** a se změnami.|
|Přidat do řešení pomocí jednoho projektu – jeden projekt|1.  Vytvořte řešení pomocí jednoho projektu.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Zavřete řešení.<br />4.  Vytvoření druhého prázdné řešení.<br />5.  Přidat dříve řízené řešení ze správy zdrojových kódů (**souboru**, **správy zdrojových kódů**, **přidat projekt ze správy zdrojových kódů**).|Přidání projektu se zobrazí v **Průzkumníka řešení** a se změnami.|
|Přidat do řešení – řešení do správy zdrojového kódu podle výběru|1.  Vytvoření řešení s projektem.<br />2.  Přidáte jenom řešení do správy zdrojového kódu jako výběr. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />3.  Zavřete řešení.<br />4.  Vytvoření nového řešení.<br />5.  Přidat dříve řízené řešení ze správy zdrojových kódů (**souboru**, **správy zdrojových kódů**, **přidat projekt ze správy zdrojových kódů**).|`Result from Step 2:`<br /><br /> Projekt není pod správou zdrojových kódů.<br /><br /> `Result from Step 5:`<br /><br /> Pokud první řešení mělo položky řešení, není možné je přidat ze správy zdrojového kódu, takže se nezobrazí.<br /><br /> Projekt z první řešení se zobrazí jako nedostupné.|

## <a name="see-also"></a>Viz také
- [Testovací příručka pro moduly plug-in správy zdrojového kódu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)