---
title: Dotazování Edit Query Save (řízení zdrojového balíčku VSPackage) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- QEQS events
- Query Edit Query Save events
- source control packages, Query Edit Query Save events
ms.assetid: c360d2ad-fe42-4d65-899d-d1588cc8a322
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d001e324352c566d71e66ae26d769cc8f3c2f644
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55011514"
---
# <a name="query-edit-query-save-source-control-vspackage"></a>Události QEQS (Query Edit Query Save) (balíček VSPackage správy zdrojového kódu)
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] editory můžete vysílat události dotazu upravit dotaz uložit (QEQS). [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Zdrojový ovládací prvek se zakázaným inzerováním implementuje QEQS služby tak, aby se příjemce události QEQS. Tyto události jsou pak přeneseny na aktuálně aktivní zdrojového balíčku VSPackage. Ovládací prvek active zdroje balíčku VSPackage implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> a její metody. Metody `IVsQueryEditQuerySave2` rozhraní se běžně označují jako okamžitě předtím, než se dokument upravovat poprvé a bezprostředně před uložení dokumentu.  
  
## <a name="queryeditquerysave-events"></a>QueryEditQuerySave Events  
 Ovládací prvek zdroje balíčku VSPackage musí zpracovávat události QEQS implementací `IVsQueryEditQuerySave2` rozhraní a metody potřebné. Níže je uveden stručný popis dvě metody, které sady VSPackage musí implementovat minimálně. Skutečná implementace musí být v souladu s logiky model správy zdrojového kódu.  
  
### <a name="queryeditfiles-method"></a>QueryEditFiles – metoda  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> Se volá, když žádné projekty ani editor chce změnit soubor. V ideálním případě by tato metoda je volána *před* změny souboru a pokud je soubor uložen. Při vyvolání, `IVsQueryEditQuerySave2::QueryEditFiles` metoda zkontroluje, jestli jsou dané soubory pod správou zdrojových kódů, určuje, zda musí být rezervován a určuje, zda že je možné znovu zavést. Pokud okolností zabránit soubory upravovat, `IVsQueryEditQuerySave2::QueryEditFiles` metoda říká volající program zrušit úpravy. Je také možné pro volajícího k určení režimu vyvolání. Tato metoda přebírá v "bezobslužný" režim akce jenom v případě, že nezpůsobí žádné uživatelské rozhraní zobrazit. Pokud nevyhnutelné uživatelské rozhraní, musí být vrácena příznak, který označuje problém.  
  
 Metoda chová transakčním způsobem; To znamená pokud na jeden soubor je zrušena upravit, upravit se zrušila, pro všechny soubory. Naopak pokud je povoleno upravit, je povoleno pro všechny soubory. Pokud tato metoda umožňuje úpravy jednou pro danou sadu souborů, musí vždy povolit úpravy při dalších volání pro stejnou sadu souborů. Povolit úpravy smyčky pokračuje, dokud uzavřeno, uložit a znovu načíst; soubory dokud změnit jejich atributy (Vlastnosti); nebo dokud zdrojový balíček ovládací prvek se změní. Případy, které je třeba zvážit při implementaci `IVsQueryEditQuerySave2::QueryEditFiles` metoda zahrnout více souborů, speciální soubory, zrušit od uživatele a úpravy v paměti.  
  
### <a name="querysavefiles-method"></a>QuerySaveFiles – metoda  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> Se volá, když žádné projekty ani editoru je potřeba uložit sady souborů. Při vyvolání, `IVsQueryEditQuerySave2::QuerySaveFiles` – metoda zkontroluje, jestli jsou dané soubory jen pro čtení a zda jsou pod správou zdrojových kódů. Pokud soubory musí být rezervován, volání se deleguje na zdrojový balíček ovládacího prvku. Pokud okolností zabránit soubory se ukládá `IVsQueryEditQuerySave2::QuerySaveFiles` metoda zapotřebí sdělit editor k uložení zrušit. Stejně jako u `IVsQueryEditQuerySave2::QueryEditFiles` metoda, je možné pro volajícího k určení režimu vyvolání. Tato metoda přebírá v "bezobslužný" režim akce jenom v případě, že nezpůsobí žádné uživatelské rozhraní zobrazit. Pokud nevyhnutelné uživatelské rozhraní, musí být vrácena příznak, který označuje problém.  
  
 Tato metoda se musí chovat transakčním způsobem; To znamená pokud na jeden soubor je zrušena uložit, uložit se zrušila, pro všechny soubory. Naopak pokud je povoleno ukládání, musí být povoleno pro všechny soubory. Stejně jako u `IVsQueryEditQuerySave2::QueryEditFiles` metody, případy, které je třeba zvážit při implementaci `IVsQueryEditQuerySave2::QuerySaveFiles` metoda zahrnout více souborů, speciální soubory, zrušit od uživatele a úpravy v paměti.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>