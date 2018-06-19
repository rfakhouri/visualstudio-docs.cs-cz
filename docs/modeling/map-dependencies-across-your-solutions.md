---
title: Mapy kódu
ms.date: 05/16/2018
ms.topic: conceptual
f1_keywords:
- vs.progression.codemap
- vs.progression.standardgraphsdialog
helpviewer_keywords:
- DGML
- graph documents
- code visualization [Visual Studio]
- dependencies, visualizing
- dependency graphs
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 553e2437abc2d8f498b556300a9266c9e79297f7
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
ms.locfileid: "34265562"
---
# <a name="map-dependencies-with-code-maps"></a>Mapování závislostí s mapy kódu

Závislosti mezi kódu můžete vizualizovat vytvořením Mapa kódu. Kód mapuje nápovědu najdete v části Jak vyhovuje kód společně bez přečtení prostřednictvím soubory a řádků kódu.

![Zobrazení závislostí napříč vaším řešením](../modeling/media/codemapsmainintro.png)

Použití map kódu, musíte Visual Studio Enterprise nebo Professional edition. Funkce map kódu v edice Professional je něco víc omezený než v edici Enterprise.

> [!NOTE]
> Před sdílením mapy vytvořené v aplikaci Visual Studio Enterprise s ostatními uživateli, kteří používají Visual Studio Professional, ujistěte se, že jsou zobrazené všechny položky na mapě (například skryté položky, rozšířená skupiny a propojení mezi skupiny).

Můžete namapovat závislosti pro kód v těchto jazycích:

- Visual C# nebo Visual Basic v řešení nebo sestavení (*.dll* nebo *.exe*)

- Nativní nebo spravovaný kód C nebo C++ v projektech Visual C++, soubory hlaviček (*.h* nebo `#include`), nebo binárních souborů

- X ++ projekty a sestavení vytvořené z modulů .NET pro aplikace Microsoft Dynamics AX

> [!NOTE]
> Pro projekty než C# nebo Visual Basic jsou méně možností pro spuštění Mapa kódu nebo přidání položky do existující mapu kódu. Nelze například klikněte pravým tlačítkem na objekt v textovém editoru projektu C++ a přidat jej do Mapa kódu. Však můžete můžete přetáhnout kódu jednotlivých elementů nebo soubory z **Průzkumníku řešení**, **zobrazení tříd**, a **Prohlížeč objektů**.

## <a name="install-code-map-and-live-dependency-validation"></a>Mapa kódu instalace a ověření za provozu závislostí

K vytvoření mapy kódu ve Visual Studio 2017, nejdřív nainstalovat **Mapa kódu** a **Live ověření závislostí** součásti:

1. Otevřete **instalační program sady Visual Studio**. Který můžete otevřít z nabídky Start nebo v sadě Visual Studio výběrem **nástroje** > **funkcí a nástrojů pro získání**.

1. Vyberte **jednotlivých součástí** kartě.

1. Přejděte dolů k položce **Code nástroje** a vyberte **Mapa kódu** a **Live ověření závislostí**.

   ![Mapa kódu a ověření Live závislost součásti v instalační program Visual Studio](media/modeling-components.png)

1. Vyberte **upravit**.

   **Mapa kódu** a **Live ověření závislostí** součásti zahájení instalace. Můžete být vyzváni, abyste zavřete Visual Studio.

## <a name="add-a-code-map"></a>Přidat mapu kódu

Můžete vytvořit mapu prázdný kód a přetáhněte položky na jeho, včetně odkazů na sestavení, soubory a složky, nebo může Generovat mapu kódu pro všechny nebo součástí vašeho řešení.

Chcete-li přidat mapu prázdný kód:

1. V **Průzkumníku**, otevřete místní nabídku pro vaše řešení nejvyšší úrovně uzlu. Zvolte **přidat** > **novou položku**.

2. V **přidat novou položku** dialogové okno, v části **nainstalovaná**, vyberte **Obecné** kategorie.

3. Vyberte **směrované Document(.dgml) grafu** šablony a potom vyberte **přidat**.

   > [!TIP]
   > Tato šablona se nemusí zobrazit abecedně, takže přejděte dolů na konec seznamu šablony, pokud ho nevidíte.

   Ve vašem řešení se zobrazí prázdnou mapu **položky řešení** složky.

Podobně můžete vytvořit nový soubor mapy kódu bez přidání do řešení výběrem **architektura** > **nové Mapa kódu** nebo **soubor**  >  **Nové** > **soubor**.

## <a name="generate-a-code-map-for-your-solution"></a>Generovat mapu kódu pro řešení

Pokud chcete zobrazit všechny závislosti ve vašem řešení:

1. Na řádku nabídek zvolte **architektura** > **Generovat mapu kódu pro řešení**. Pokud váš kód nezměnila od poslední vytvořené, můžete vybrat **architektura** > **Generovat mapu kódu pro řešení bez vytvoření** místo.

   ![Generování příkazu mapy kódu](../modeling/media/codemapsarchitecturemenu.png)

   Mapu se generuje zobrazující sestavení nejvyšší úrovně a agregované odkazy mezi nimi. Širší souhrnného propojení, další závislosti reprezentuje.

2. Použití **legendy** položky kód (například tříd, metod a vlastností) a typy vztahů (například dědí z tlačítko na panelu nástrojů Mapa kódu zobrazit nebo skrýt seznam ikony typu projektu (například Test, webové a Phone projektu) Implementuje a volání).

   ![Graf závislostí nejvyšší úrovně sestavení](../modeling/media/dependencygraph_toplevelassemblies.png)

   Tento příklad řešení obsahuje složky řešení (**testy** a **součásti**), projektů testů, webové projekty a sestavení. Ve výchozím nastavení zobrazí všechny vztahy členství ve skupině jako *skupiny*, které můžete rozbalit nebo sbalit. **Externals** skupina obsahuje nic mimo řešení, včetně závislostí platformy. Externí sestavení obsahuje pouze položky, které jsou používány. Ve výchozím nastavení jsou na mapě pro lepší přehlednost skrytá základní typy systému.

3. Můžete rozbalit mapy, rozbalte položku skupiny, které představují projekty a sestavení. Můžete rozbalit vše, co stisknutím **CTRL + A** vyberte všechny uzly a pak vyberete **skupiny**, **rozbalte** z místní nabídky.

   ![Rozbalení všech skupin v mapě kódu](../modeling/media/codemapsexpandallgroups.png)

4. To však nemusí být užitečné pro velké řešení. Ve skutečnosti pro komplexní řešení, omezení paměti může zabránit vám v rozšíření všechny skupiny. Místo toho pokud chcete zobrazit v jednotlivých uzlu, rozbalte ho. Přesuňte ukazatel myši nad uzel a potom klikněte na dvojitou šipku (šipka) dolů Jakmile se zobrazí.

   ![Rozšíření uzlu v mapě kódu](../modeling/media/dependencygraph_containment.png)

   Nebo pomocí klávesnice tak, že vyberete položku pak stisknete klávesu plus (**+**). Chcete-li prozkoumat podrobněji úrovně kódu, proveďte stejný pro obory názvů, typy a členy.

   > [!TIP]
   > Další informace o práci s kódem mapuje pomocí myši, klávesnice a dotykového ovládání, naleznete v tématu [Procházet a uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md).

5. Pro zjednodušení mapy a zaměřit se na jednotlivé části, zvolte **filtry** na panelu nástrojů Mapa kódu a vyberte pouze typy uzlů a odkazy vás zajímá. Například můžete skrýt všechny složky řešení a sestavení kontejnery.

   ![Zjednodušení mapy filtrováním kontejnery](../modeling/media/codemapsfilterfoldersassemblies.png)

   Skrytí nebo odebráním jednotlivých skupin a položek z mapování, aniž by to ovlivnilo kód základní řešení můžete také zjednodušit mapy.

6. Pokud chcete zobrazit vztahy mezi položkami, vyberte je v mapě. Barvy odkazy označují typy relace, jak je znázorněno **legendy** podokně.

   ![Zobrazení závislostí napříč vaším řešením](../modeling/media/codemapsmainintro.png)

   V tomto příkladu jsou odkazy na fialové volání, jsou odkazy na desítkovém odkazy a světla modré odkazy jsou přístup k poli. Zelená odkazy mohou být dědičnosti nebo mohou být *agregovat odkazy* indikující, více než jeden typ vztahu (nebo *kategorie*).

   > [!TIP]
   > Pokud se zobrazí zelená odkaz, nemusí to znamená, že je právě vztah dědičnosti. Může také být volání metod, ale tyto skryt vztah dědičnosti. Pokud chcete zobrazit konkrétní typy odkazů, pomocí zaškrtávacích políček v **filtry** podokně typy nemusí.

7. Chcete-li získat další informace o položku nebo odkaz, přesuňte ukazatel myši nad jeho se zobrazí popisek. Ukazuje to podrobností element kódu nebo kategorie, které představuje odkaz.

   ![Zobrazit kategorie relace](../modeling/media/codemapsshowlinkcatgories.png)

8. Chcete-li zkontrolujte položky a závislosti reprezentována souhrnného propojení, nejprve vyberte odkaz a pak otevřete jeho místní nabídky. Zvolte **zobrazit přidání odkazů** (nebo **zobrazit přidání odkazů na nové Mapa kódu**). To rozbalí skupiny na obou koncích propojení a zobrazuje pouze položky a závislosti, které se účastní v odkazu.

9. Chcete-li se zaměřit na konkrétní části mapy, můžete nadále odebrat položky, které nechcete. Například přejdete do zobrazení třídy a člen, jednoduše filtrovat všechny uzly oboru názvů v **filtry** podokně.

   ![Přecházení na úrovni třídy a člen](../modeling/media/dependencygraph_expandedselectedgroups_2012.png)

10. Dalším způsobem, abyste se mohli zaměřit na mapě komplexní řešení je generovat nové mapování obsahující vybrané položky z existující mapu. Uložení **Ctrl** , že při výběru položky, které chcete se zaměřit na, otevřete místní nabídku a vyberte **nový graf z výběru**.

   ![Zobrazit vybrané položky na nové mapě kódu](../modeling/media/codemapsshowonnewmap.png)

11. Obsahující kontext se přenášejí do nové mapování. Skrýt složky řešení a žádné kontejnery, které nechcete zobrazit pomocí **filtry** podokně.

   ![Filtrovat kontejnery zjednodušit zobrazení](../modeling/media/codemapsexpandnewgroups.png)

12. Skupiny rozbalte a vyberte položky v mapě zobrazíte vztahy.

   ![Vyberte položky, chcete-li zobrazit vztahy](../modeling/media/codemapsviewnewrelationships.png)

Viz také:

- [Procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)
- [Přizpůsobení map kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md)
- Nalezení potenciálních problémů v kódu pomocí [systémem analyzátoru](../modeling/find-potential-problems-using-code-map-analyzers.md)

## <a name="view-specific-dependencies-in-a-code-map"></a>Zobrazení konkrétní závislostí v mapě kódu

Předpokládejme, že máte revize kódu provádět v některé soubory s změny čekající na zpracování. Pokud chcete zobrazit závislosti ve tyto změny, můžete vytvořit Mapa kódu z těchto souborů.

   ![Zobrazit konkrétní závislosti na mapě kódu](../modeling/media/codemapsspecificdependenciesintro.png)

1. V **Průzkumníku**, vyberte projekty, odkazy na sestavení, složky, soubory, typy nebo členy, které chcete namapovat.

   ![Vyberte položky, které chcete namapovat](../modeling/media/codemapsselectinsolutionexplorer.png)

1. Na **Průzkumníku řešení** nástrojů vyberte **zobrazit na mapě kódu** ![vytvořit nový graf z vybrané uzly tlačítko](../modeling/media/createnewgraphfromselectedbutton.gif). Nebo, otevřete místní nabídku pro jeden nebo skupinu položek a zvolte **zobrazit na mapě kódu**.

   Můžete také přetáhnout položky z **Průzkumníku řešení**, **zobrazení tříd**, nebo **Prohlížeč objektů**, do [nové](#add-a-code-map) nebo mapovat existující kód. Chcete-li zahrnout nadřazenou hierarchii pro své položky, stiskněte a podržte **Ctrl** klíče při přetahování položek, nebo použít **zahrnují nadřazené položky** tlačítka na panelu nástrojů map kódu k určení výchozí akci. Také můžete přetáhnout soubory sestavení mimo aplikaci Visual Studio, například z **Průzkumníka Windows**.

   > [!NOTE]
   > Při přidání položky z projektu, jež jsou sdílena mezi více aplikacemi, jako je Windows Phone nebo Microsoft Store, tyto položky se zobrazí na mapě s projekt aktuálně aktivní aplikace. Pokud změníte kontext na jiný projekt aplikace a přidáte další položky ze sdíleného projektu, tyto položky se nyní zobrazí s nově aktivním projektem aplikace. Operace, které provádíte s položkou na mapě, se vztahují pouze na ty položky, které sdílejí stejný kontext.

3. Mapa zobrazuje vybrané položky v rámci jejich obsahující sestavení.

   ![Vybrané položky zobrazené jako skupiny na mapě](../modeling/media/codemapsshowitemsfromsolnexplorer.png)

4. Chcete-li prozkoumat položky, rozbalte je. Přesuňte ukazatel myši nad položku a pak klikněte na ikonu dvojité šipky (šipka) dolů, když se objeví.

   ![Rozbalte uzel v mapě kódu](../modeling/media/dependencygraph_containment.png)

   Chcete-li rozšířit všechny položky, vyberte je pomocí **Ctrl**+**A**, otevřete místní nabídku pro mapu a zvolte **skupiny**  >   **Rozbalte položku**. Však tato možnost není dostupná, pokud se zvětšující všechny skupiny vytvoří nepoužitelná mapy nebo problémy s pamětí.

5. Rozbalte položky, které vás zajímají, až na úrovni třídy a člen v případě potřeby i nadále.

   ![Rozšíření skupiny na úrovni třídy a člen](../modeling/media/codemapsexpandtoclassandmember.png)

   Pokud chcete zobrazit členy, kteří jsou v kódu, ale nezobrazí na mapě, klikněte **znovu načíst podřízené objekty** ikonu ![znovu načíst ikonu podřízené objekty](../modeling/media/dependencygraph_deletednodesicon.png) v levém horním rohu skupinu.

6. Pokud chcete zobrazit další položky související s ohledem na mapě, vyberte jeden a zvolte **zobrazit související** na panelu nástrojů Mapa kódu, pak vyberte typ souvisejících položek, které chcete přidat do mapy. Nebo vyberte jednu nebo více položek, otevřete místní nabídku a pak zvolte **zobrazit** možnost pro typ související položky pro přidání do mapy. Příklad:

    Pro **sestavení**, vyberte:

    |||
    |-|-|
    |**Zobrazit tuto odkazy na sestavení**|Přidejte sestavení, na které odkazuje toto sestavení. Externí sestavení se zobrazí v **Externals** skupiny.|
    |**Zobrazit to odkazování na sestavení**|Přidejte sestavení do řešení, která odkazují na toto sestavení.|

    Pro **obor názvů**, zvolte **zobrazit sestavení obsahující**, pokud není viditelná.

    Pro **třída** nebo **rozhraní**, vyberte:

    |||
    |-|-|
    |**Zobrazit základní typy**|V případě třídy přidejte základní třídu a implementovaná rozhraní.<br /><br /> V rámci rozhraní přidejte základní rozhraní.|
    |**Zobrazit odvozené typy**|V případě třídy přidejte odvozené třídy.<br /><br /> V rámci rozhraní přidejte odvozené rozhraní a implementaci tříd nebo struktur.|
    |**Zobrazit typy tento odkazy**|Přidejte všechny třídy a jejich členy, které tato třída používá.|
    |**Zobrazit typy to odkazování na**|Přidejte všechny třídy a jejich členy, které tuto třídu používají.|
    |**Zobrazení obsahujícího Namespace**|Přidáte obor názvů nadřazené.|
    |**Zobrazit obsahující Namespace a sestavení**|Přidejte hierarchii nadřazeného kontejneru.|
    |**Zobrazit všechny základní typy**|Přidejte rekurzivně hierarchii základní třídy nebo rozhraní.|
    |**Zobrazit všechny odvozené typy**|V případě třídy přidejte všechny odvozené třídy rekurzivně.<br /><br /> V rámci rozhraní přidejte rekurzivně veškerá odvozená rozhraní a implementaci tříd nebo struktur.|

     Pro **metoda**, vyberte:

    |||
    |-|-|
    |**Zobrazit metody, které volá**|Přidejte metody, které tato metoda volá.|
    |**Zobrazit tuto odkazy na pole**|Přidejte pole, na která odkazuje tato metoda.|
    |**Zobrazit obsahující typ**|Přidejte typ nadřazené.|
    |**Zobrazit obsahující typ, Namespace a sestavení**|Přidejte hierarchii nadřazeného kontejneru.|
    |**Zobrazit přepsání metody**|V případě metody, která přepíše jiné metody nebo implementuje metodu rozhraní, přidejte všechny abstraktní nebo virtuální metody základních tříd, které jsou přepsány, a případně metodu rozhraní, které je implementováno.|

     Pro **pole** nebo **vlastnost**, vyberte:

    |||
    |-|-|
    |**Zobrazit obsahující typ**|Přidejte typ nadřazené.|
    |**Zobrazit obsahující typ, Namespace a sestavení**|Přidejte hierarchii nadřazeného kontejneru.|

    ![Zobrazit metody volá tento člen](../modeling/media/codemapsshowrelatedmethods.png)

7. Mapa znázorňuje vztahy. V tomto příkladu mapa znázorňuje metodu volá `Find` metoda a jejich umístění v řešení nebo externě.

   ![Zobrazit konkrétní závislosti na mapě kódu](../modeling/media/codemapsspecificdependenciesintro.png)

8. Pro zjednodušení mapy a zaměřit se na jednotlivé části, zvolte **filtry** na panelu nástrojů Mapa kódu a vyberte pouze typy uzlů a odkazy vás zajímá. Například Vypněte displej řešení složek, sestavení a obory názvů.

   ![Použijte podokno filtru pro zjednodušení zobrazení](../modeling/media/almcodemapfilterpane.png)

## <a name="see-also"></a>Viz také

- [Video: porozumět návrhu z kódu pomocí map kódu v sadě Visual Studio 2015](https://channel9.msdn.com/Events/Visual-Studio/Connect-event-2015/502)]
- [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)
- [Mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
- [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)
- [Procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)
- [Přizpůsobení map kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md)
