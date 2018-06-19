---
title: Najdete v části závislosti mezi C++ zdrojové soubory a soubory hlaviček
ms.date: 05/16/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.workload:
- multiple
ms.openlocfilehash: d274241700dfdac393544f554f7025ea4d0bcb46
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
ms.locfileid: "34263770"
---
# <a name="code-maps-for-c-projects"></a>Mapy kódu pro projekty C++

Pokud chcete vytvořit podrobnější mapy pro projekty C++, nastavte možnost Procházet informace kompilátoru (**/FR**) na těchto projekty. Jinak se objeví zpráva s dotazem, zda chcete tuto možnost nastavit. Pokud vyberete **OK**, nastaví tato možnost pouze aktuální mapy. Můžete skrýt zprávu pro všechny novější mapy.

Když otevřete řešení, které obsahuje projekty Visual C++, může trvat nějakou dobu, než se aktualizuje databáze technologie IntelliSense. Během této doby, není možné vytvořit map kódu hlavičky (*.h* nebo `#include`) soubory, dokud nebude dokončeno databázi IntelliSense aktualizace. Na stavovém řádku v dolní části sady Visual Studio můžete sledovat průběh aktualizace.

- Pokud chcete zobrazit závislosti mezi všechny zdrojové soubory a soubory hlaviček ve vašem řešení, vyberte **architektura** > **generovat grafu zahrnout soubory**.

   ![Graf závislostí pro nativní kód](../modeling/media/dependencygraphgeneral_nativecode.png)

- Chcete-li zobrazit závislosti mezi aktuálně otevřených souborů a související zdrojové soubory a soubory hlaviček, otevřete zdrojový soubor nebo soubor hlaviček. Otevřete soubor místní nabídky kdekoli v souboru. Zvolte **Generovat graf zahrnout soubory**.

   ![Graf závislostí první úrovně pro soubor h](../modeling/media/dependencygraph_native_firstlevel.png)

## <a name="troubleshoot-code-maps-for-c-and-c-code"></a>Řešení potíží s map kódu pro kód C a C++

Tyto položky nejsou podporovány pro kód C a C++:

- Základní typy nezobrazí v maps, které zahrnují nadřazenou hierarchii.

- Většina **zobrazit** položky nabídky nejsou k dispozici pro kód C a C++.

Při vytváření map kódu pro kód C a C++, může dojít k těmto problémům:

|**Problém**|**Možná příčina**|**Řešení**|
|---------------|------------------------|--------------------|
|Mapa kódu se nepodařilo vygenerovat.|V řešení nebyly úspěšně sestaveny žádné projekty.|Opravte chyby sestavení, které nastaly a pak znovu vygenerovat mapy.|
|Visual Studio přestane reagovat, při pokusu o generování mapy kódu z **architektura** nabídky.|Soubor databáze programů (.pdb) může být poškozen.<br /><br /> Soubor .pdb ukládá informace o ladění, jako je typ, metoda a informace zdrojového souboru.|Znovu sestavte řešení a potom akci opakujte.|
|Určitá nastavení pro databázi procházení IntelliSense jsou zakázána.|V sadě Visual Studio může být zakázáno určitá nastavení IntelliSense **možnosti** dialogové okno.|Chcete-li tato nastavení povolit, zapněte je.<br /><br /> V tématu [možnosti, textový Editor, C/C++, Upřesnit](../ide/reference/options-text-editor-c-cpp-advanced.md).|
|Zpráva **neznámé metody** se zobrazí v uzlu metoda.<br /><br /> K tomuto problému dochází, protože nelze vyřešit název metody.|Binární soubor nemusí mít základní tabulku přemístění.|Zapnout **/FIXED:NO** možnost v linkeru.|
||Soubor databáze programů (.pdb) nemusí být vytvořen.<br /><br /> Soubor .pdb ukládá informace o ladění, jako je typ, metoda a informace zdrojového souboru.|Zapnout **/DEBUG** možnost v linkeru.|
||V očekávaných umístěních nelze otevřít nebo najít soubor .pdb.|Ujistěte se, že v předpokládaném umístění existuje soubor .pdb.|
||Informace o ladění byly ze souboru .pdb odstraněny.|Pokud **/PDBSTRIPPED** možnost byl použit v linkeru, místo toho zahrnout soubor .pdb dokončení.|
||Volající není funkcí a je převodní rutinou v binárním souboru nebo ukazatelem v datové sekci.|Pokud má volající převodu, zkuste použít `_declspec(dllimport)` předejdete převodu.|

## <a name="see-also"></a>Viz také

- [Mapování závislostí s mapy kódu](../modeling/map-dependencies-across-your-solutions.md)