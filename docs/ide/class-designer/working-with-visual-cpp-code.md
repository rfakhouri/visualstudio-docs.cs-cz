---
title: Práce s kódem jazyka Visual C++ (návrhář tříd)
ms.date: 06/21/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.cpplimitation
helpviewer_keywords:
- Visual C++, Class Designer
- Class Designer, Visual C++ support
- Class Designer, limitations
- Class Designer, tasks in Visual C++
- Visual C++, class diagrams
- C++, class diagrams
- C++, Class Designer
ms.assetid: f5b40921-2ef7-4de0-b595-45b44c79ffa6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 1497730cf7c2b2e9abc17ec6cb82179deebb30d7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54948047"
---
# <a name="work-with-visual-c-code-in-class-designer"></a>Práce s kódem jazyka Visual C++ v Návrháři tříd

**Návrhář tříd** zobrazí vizuální návrhová plocha volána *diagram tříd* , který obsahuje vizuální reprezentaci prvků kódu ve vašem projektu. Diagramy tříd můžete navrhovat a zobrazovat třídami a ostatními typy v projektu.

**Návrhář tříd** podporuje následující prvky kódu jazyka C++:

- Třídy (se podobá obrazec spravovanou třídu s tím rozdílem, že může mít více vztahů dědičnosti)

- Anonymní třídy (zobrazí se vygenerovaný název anonymního typu zobrazení tříd)

- Třída šablony

- Struktura

- Výčet

- (Zobrazí se po zpracování zobrazení makro) – makro

- Definice TypeDef

> [!NOTE]
> To však není stejný jako diagram tříd UML, který vytvoříte v projektu modelování. Další informace najdete v tématu [diagramů tříd UML: Referenční dokumentace](../../modeling/create-uml-modeling-projects-and-diagrams.md).

## <a name="troubleshoot-type-resolution-and-display-issues"></a>Řešení potíží typu řešení a s problémy zobrazení

### <a name="location-of-source-files"></a>Umístění zdrojových souborů

**Návrhář tříd** přehled o umístění zdrojových souborů. Proto, pokud změníte strukturu projektu nebo přesunout zdrojové soubory v projektu, **návrhář tříd** může dojít ke ztrátě sledování typu (zejména zdrojového typu definice typu základní třídy a přidružení typů). K chybě může dojít například **je návrhář tříd nemůže zobrazit tento typ**. Pokud tak učiníte, přetáhněte do diagramu tříd znovu a znovu zobrazit přemístění nebo upravila zdrojový kód.

### <a name="update-and-performance-issues"></a>Problémy aktualizace a výkonu

Pro projekty Visual C++ může trvat přibližně 30 – 60 sekund změny ve zdrojovém souboru se zobrazí v diagramu tříd. Toto zpoždění může také způsobit **návrhář tříd** vyvolat chybu **nenašly se žádné typy ve výběru**. Pokud obdržíte chybu takovou situaci, klikněte na tlačítko **zrušit** v chybové zprávě a vyčkat, než prvek kódu se zobrazí v **zobrazení tříd**. Až to uděláte **návrhář tříd** by měl mít možnost pro zobrazení typu.

Pokud diagram tříd se neaktualizuje se změny provedené v kódu, může být potřeba diagram zavřít a znovu ji spusťte.

### <a name="type-resolution-issues"></a>Typ řešení problémů

**Návrhář tříd** nemusí být možné přeložit typy z následujících důvodů:

- Typ není v projektu nebo sestavení, který neodkazuje projekt, který obsahuje diagram třídy. Chcete-li opravit tuto chybu, přidejte odkaz na projekt nebo sestavení obsahující typ. Další informace najdete v tématu [Správa odkazů v projektu](../managing-references-in-a-project.md).

- Typ není ve správném oboru, takže **návrhář tříd** nelze najít. Ujistěte se, že kód není chybí `using`, `imports`, nebo `#include` příkazu. Ujistěte se také, že nebyly vyjme typ (nebo související typ) z oboru názvů, ve kterém bylo původně umístěná.

- Typ neexistuje (nebo má zakomentované). Chcete-li tuto chybu opravit, ujistěte se, že nejsou označené jako komentář nebo odstranit typ.

- Typ je umístěn v knihovně odkazuje direktivu #import. Možných řešení je ruční přidání generovaný kód (soubor .tlh) #include – direktiva v souboru hlaviček.

- Ujistěte se, že **návrhář tříd** podporuje typ, který jste zadali. Zobrazit [omezení pro prvky kódu C++](#limitations-for-c-code-elements).

Chyba se pravděpodobně chcete zobrazit pro řešení problému s typem je **kód nemohl být nalezen jeden nebo více obrazců v diagramu tříd '\<element > "**. Tato chybová zpráva nemusí znamenat, že je váš kód v chybě. Označuje, že jste byli pouze tento návrhář tříd nemůže zobrazit váš kód. Vyzkoušejte následující míry:

- Ujistěte se, že typ existuje. Ujistěte se, že nejsou neúmyslně zakomentované nebo odstranili zdrojový kód.

- Došlo k pokusu o přeložení typu. Typ může být v projektu nebo sestavení, který neodkazuje projekt, který obsahuje diagram třídy. Chcete-li opravit tuto chybu, přidejte odkaz na projekt nebo sestavení obsahující typ. Další informace najdete v tématu [Správa odkazů v projektu](../managing-references-in-a-project.md).

- Ujistěte se, že typ je ve správném oboru tak, aby ji mohli najít návrhář tříd. Ujistěte se, že kód není chybí `using`, `imports`, nebo `#include` příkazu. Ujistěte se také, že nebyly vyjme typ (nebo související typ) z oboru názvů, ve kterém bylo původně umístěná.

### <a name="troubleshoot-other-error-messages"></a>Řešení potíží s další chybové zprávy

Pomoc při řešení problémů s chybami a upozorněními můžete najít na veřejných fórech Microsoft Developer Network (MSDN). Zobrazit [návrháře fórum Visual Studio třídy](http://go.microsoft.com/fwlink/?linkid=160754).

## <a name="limitations-for-c-code-elements"></a>Omezení pro prvky kódu jazyka C++

- Při načtení projektu Visual C++ **návrhář tříd** funguje způsobem jen pro čtení. Můžete změnit diagramu tříd, ale nemůžete ukládat změny z diagramu tříd zpět ke zdrojovému kódu.

- **Návrhář tříd** podporuje pouze nativní C++ sémantiku. Pro projekty Visual C++, které jsou kompilovány do spravovaného kódu **návrhář tříd** budete vizualizovat pouze prvky kódu, které jsou nativní typy. Proto přidání diagramu tříd do projektu, ale **návrhář tříd** nebude možné vizualizovat prvků, ve kterém `IsManaged` je nastavena na `true` (tzn. typy hodnot a odkazové typy).

- Pro projekty Visual C++ **návrhář tříd** čte pouze definici typu. Předpokládejme například, definice typu v souboru hlaviček (.h) a definovat jeho členy v souboru implementace (.cpp). Pokud vyvoláte "Zobrazit Diagram tříd" v souboru implementace (.cpp) **návrhář tříd** nezobrazí nic. Další příklad – pokud vyvoláte "Zobrazit Diagram tříd" na soubor .cpp, který používá `#include` příkazu zahrnout další soubory, ale neobsahuje žádné definice tříd skutečné **návrhář tříd** znovu nezobrazí nic.

- Soubory IDL (.idl), které definují rozhraní COM a knihoven typů, se nezobrazují v diagramech, pokud jsou kompilovány do nativního kódu C++.

- **Návrhář tříd** nepodporuje globální funkce a proměnné.

- **Návrhář tříd** nepodporuje sjednocení. Toto je speciální typ třídy, ve kterém je paměť přidělená je pouze množství potřebné pro největší datový člen Evropské unie.

- **Návrhář tříd** nezobrazuje základní datové typy, jako `int` a `char`.

- **Návrhář tříd** nezobrazuje typy, které jsou definovány mimo aktuální projekt, pokud projekt nemá správné odkazy na tyto typy.

- **Návrhář tříd** můžete zobrazit, ale ne vztahy mezi vnořeného typu a ostatními typy vnořené typy.

- **Návrhář tříd** nemůže zobrazit typy, které jsou neplatné nebo které jsou odvozeny od typu void.

## <a name="see-also"></a>Viz také:

- [Navrhování a zobrazování tříd a typů](designing-and-viewing-classes-and-types.md)
- [Další informace o chybách Návrháře tříd](additional-information-about-errors.md)
- [Třídy jazyka Visual C++ v Návrháři tříd](visual-cpp-classes.md)
- [Struktury jazyka Visual C++ v Návrháři tříd](visual-cpp-structures.md)
- [Výčty jazyka Visual C++ v Návrháři tříd](visual-cpp-enumerations.md)
- [Definice Typedefs jazyka Visual C++ v Návrháři tříd](visual-cpp-typedefs.md)
