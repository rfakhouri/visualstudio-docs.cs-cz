---
title: Strukturujte svá řešení modelování
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: a18dbf13929163e6f4a0f3d123fe393a188d0830
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="structure-your-modeling-solution"></a>Strukturujte svá řešení modelování
Efektivně používat modely v projektu vývoj, musí být členy týmu mohou pracovat na modely z různých částí projektu ve stejnou dobu. Toto téma navrhuje schéma pro dělení aplikace do různých částí, které odpovídají vrstvy v celkovou rozvrstvení diagram.

 Ke spuštění na projektu nebo dílčí projekt rychle, je užitečné používat šablony projektu, který následuje strukturu projektu, které jste vybrali. Toto téma popisuje postup vytvoření a použití takových šablony.

 Toto téma předpokládá, že pracujete na projekt, který je dostatečně velké na to, aby několik členové týmu a pravděpodobně má několik týmů. Kód a modely projektu jsou uloženy v systému správy zdrojů, jako [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)]. Alespoň některé členy týmu použijte sadu Visual Studio pro vývoj modely a ostatní členové týmu můžete zobrazit modely pomocí jiné verze sady Visual Studio.

 Informace, které verze sady Visual Studio podporují jednotlivé funkce nástroje a modelování, najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="solution-structure"></a>Struktura řešení
 V projektu střední a velké strukturu týmu vychází strukturu aplikace. Každý používá řešení sady Visual Studio.

#### <a name="to-divide-an-application-into-layers"></a>K rozdělení aplikace do vrstvy

1.  Základní struktura řešení ve struktuře vaší aplikace, jako jsou webové aplikace, aplikace služby nebo aplikace pracovní plochy. Celou řadu běžných architektury popsané v [Archetypes aplikace v příručce k Microsoft aplikace architektura](http://go.microsoft.com/fwlink/?LinkId=196681).

2.  Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení, který nazýváme Architektura řešení. Toto řešení se použije k vytvoření celkového návrhu systému. Bude obsahovat modely, ale žádný kód.

     Přidáte závislost diagram toto řešení. Diagram závislostí zakreslit architekturu, kterou jste zvolili pro vaši aplikaci. Například může tyto vrstvy a jejich vzájemné závislosti zobrazit diagram: prezentace; Obchodní logika; a Data.

4.  Vytvoření samostatné řešení Visual Studio pro každou vrstvu v diagramu závislost architektury.

     Tato řešení se použije k vývoji kód vrstvy.

5.  Vytváření modelů, které budou představovat návrhů vrstvy a koncepty, které jsou společné pro všechny vrstvy. Modely uspořádejte tak, aby všechny modely si můžete prohlédnout z architektury řešení a relevantní modely si můžete prohlédnout z každé vrstvě.

     Můžete dosáhnout pomocí některé z následujících postupů. V prvním případě vytvoří samostatné modelování projekt pro každou vrstvu a druhý vytvoří jeden modelování projektu, jež jsou sdílena mezi vrstvy.

    ###### <a name="to-use-a-separate-modeling-project-for-each-layer"></a>Použít samostatné modelování projekt pro jednotlivé úrovně

    1.  Vytvořte projekt modelování v každé vrstvě řešení.

         Tento model bude obsahovat diagramy, které popisují požadavků a návrhu této vrstvy. Může také obsahovat diagramy závislosti, které ukazují vnořené vrstvy.

         Nyní máte model pro jednotlivé úrovně plus model pro Architektura aplikace. Každý model je obsažený v jeho vlastní řešení. To umožňuje členové týmu pro práci na vrstvy ve stejnou dobu.

    2.  Architektura řešení přidáte projekt modelování jednotlivých řešení vrstvy. K tomuto účelu otevřete Architektura řešení. V Průzkumníku řešení klikněte pravým tlačítkem na uzel řešení, přejděte na Přidat a pak klikněte na tlačítko **existující projekt**. Přejděte do jedné vrstvy řešení modelování projektu (.modelproj).

         Každý model se nyní zobrazí na dvě řešení: jeho "home" řešení a architektura.

    3.  Do projektu modelování každé vrstvě přidejte závislosti diagram. Začněte kopii diagram architektury závislostí. Odstraněním částí, které nejsou závislosti diagramu závislostí.

         Můžete také přidat závislost diagramy, které představují podrobné strukturu této vrstvy.

         Tyto diagramy se používají k ověření kód, který je vyvinuta v této vrstvě.

    4.  V architektuře řešení upravte požadavků a návrhu modely všechny vrstvy, které pomocí sady Visual Studio.

         V každé vrstvě řešení vyvíjet kód pro tuto vrstvu, která odkazuje na modelu. Pokud jste obsahu udělat vývoj bez použití k aktualizaci modelu stejném počítači, můžete číst modelu a vývoj kódu s použitím verze sady Visual Studio, který nelze vytvořit modely. Také mohou generovat kód z modelu v těchto verzích.

     Tato metoda zaručuje, že bude bez narušení způsobené vývojáře, kteří upravit modely vrstev ve stejnou dobu.

     Ale protože modely jsou oddělené, je obtížné najdete běžné koncepty. Každý model musí mít svůj vlastní kopii elementy, na kterých je závislá z jiných vrstev a architektura. Diagram závislostí v každé vrstvě musí být udržovány synchronizována s diagram architektury závislostí. Je obtížné spravovat synchronizaci, pokud tyto prvky změnit, i když může vyvíjet nástroje k tomu.

    ###### <a name="to-use-a-separate-package-for-each-layer"></a>Používat samostatný balíček pro jednotlivé úrovně

    1.  V řešení pro každou vrstvu přidejte projekt modelování architektury. V Průzkumníku řešení klikněte pravým tlačítkem na uzel řešení, přejděte na **přidat**a potom klikněte na **existující projekt**. Jeden modelování projektu je nyní přístupná z každé řešení: architektura projekt a projekt vývoj pro jednotlivé úrovně.

    2.  Ve sdíleném modelu, vytvořit balíček pro jednotlivé úrovně: V Průzkumníku řešení, vyberte projekt modelování. V Průzkumníku modelu UML, klikněte pravým tlačítkem na kořenový uzel modelu, přejděte na **přidat**a potom klikněte na **balíček**.

         Každý balíček bude obsahovat diagramy, které popisují požadavků a návrhu odpovídající vrstvy.

    3.  V případě potřeby přidejte místní závislostí diagramy pro interní jednotlivé úrovně.

     Tato metoda umožňuje prvky návrhu každé vrstvě odkazovat na těch, které vrstvy a společné architektury, na němž závisí.

     I když některé konflikty může způsobit souběžné úlohy na různých balíčcích, jsou poměrně snadno spravovat, protože balíčky jsou uložené v samostatné soubory.

## <a name="creating-architecture-templates"></a>Vytváření šablon architektura
 V praxi nevytvoří všech svých řešení sady Visual Studio ve stejnou dobu ale je přidat průběhu projektu. Pravděpodobně budete také použít stejnou strukturu řešení v budoucnosti projekty.  Můžete rychle vytvořit nové řešení, můžete vytvořit šablonu řešení nebo produktu project. Můžete zaznamenat šablony ve Visual Studio integrace rozšíření (VSIX), aby bylo snadné, distribuce a nainstalovat na jiných počítačích.

 Například pokud používáte často řešení, které mají prezentační, obchodní a datové vrstvy, můžete nakonfigurovat šablonu, která se vytvoří nová řešení, které mají této struktury.

#### <a name="to-create-a-solution-template"></a>Chcete-li vytvořit šablonu řešení

1.  [Stáhněte a nainstalujte v Průvodci Export šablony](http://go.microsoft.com/fwlink/?LinkId=196686), pokud jste to ještě neudělali.

2.  Vytvořte strukturu řešení, která chcete použít jako východisko pro budoucí projekty.

3.  Na **souboru** nabídky, klikněte na **exportovat šablonu jako VSIX**. **Exportovat šablonu jako průvodce VSIX** otevře.

4.  Postupujte podle pokynů v průvodci vyberte projektů, které chcete do šablony zahrnout, zadejte název a popis pro šablonu a zadejte umístění výstupu.

> [!NOTE]
>  Materiály v tomto tématu je abstrahované a parafrázována z Visual Studio Tooling doporučení ohledně architektury, zapsána pomocí Visual Studio ALM Rangers, což je spolupráce mezi nejvíce cenná Odborníci v oblasti (MVP), Microsoft Services a sady Visual Studio produktový tým a zapisovače. [Chcete-li stáhnout balíček kompletní pokyny, klikněte sem.](http://go.microsoft.com/fwlink/?LinkID=191984)

## <a name="related-materials"></a>Související materiály
 [Uspořádání a správu modely](http://channel9.msdn.com/posts/clinted/UML-with-VS-2010-Part-9-Organizing-and-Managing-Your-Models/) – video od Clint Edmondson.

 [Visual Studio Tooling doporučení ohledně architektury](../modeling/visual-studio-architecture-tooling-guidance.md) -Další informace o správě modely v týmu

## <a name="see-also"></a>Viz také

- [Použití modelů ve vývojových procesech](../modeling/use-models-in-your-development-process.md)
