---
title: Používání členů oboru názvů Microsoft.VisualStudio.TestTools.UnitTesting při testech jednotek
ms.date: 03/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: reference
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: ccc41d7cc2e1150c6c4eb9ca1e62719517b194fa
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975543"
---
# <a name="use-the-mstest-framework-in-unit-tests"></a>Použití Mstestu framework při testech jednotek

[Mstestu](<xref:Microsoft.VisualStudio.TestTools.UnitTesting>) framework podporuje jednotky testování v sadě Visual Studio. Používání tříd a členové <xref:Microsoft.VisualStudio.TestTools.UnitTesting> obor názvů při programování testování částí. Můžete taky je při jsou upřesnění testů jednotek, která byla vygenerována z kódu.

## <a name="framework-members"></a>Členy Framework

Pomáhají jasnější přehled testování framework jednotky v této části slouží k uspořádání členů <xref:Microsoft.VisualStudio.TestTools.UnitTesting> oboru názvů do skupin souvisejících funkcí.

> [!NOTE]
> Atribut elementy, jejichž názvy končit "Atribut", lze použít s nebo bez "Atribut" na konci. Například následující příklady kódu dvě pracovat stejně jako:
>
> `[TestClass()]`
>
> `[TestClassAttribute()]`

### <a name="members-used-for-data-driven-testing"></a>Používat pro testování datové členy

Nastavit testy jednotek řízené daty pomocí následující prvky. Další informace najdete v tématu [vytvořit testování částí Data-Driven](../test/how-to-create-a-data-driven-unit-test.md) a [pomocí konfiguračního souboru k definování zdroje dat](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md).

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataAccessMethod>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceElement>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceElementCollection>

## <a name="attributes-used-to-establish-a-calling-order"></a>Atributy se používají ke zřízení pořadí volání

Element kódu dekorované s jedním z následujících atributů je volána v okamžiku, kdy je zadat. Další informace najdete v tématu [anatomie testování částí](http://msdn.microsoft.com/a03d1ee7-9999-4e7c-85df-7d9073976144).

### <a name="attributes-for-assemblies"></a>Atributy pro sestavení

AssemblyInitialize a AssemblyCleanup se nazývají práva po načtení vaše sestavení a pravé před uvolněním vaše sestavení.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssemblyInitializeAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssemblyCleanupAttribute>

### <a name="attributes-for-classes"></a>Atributy pro třídy

ClassInitialize a ClassCleanup se nazývají práva po načtení třídě a pravé před uvolněním třídě.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ClassInitializeAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ClassCleanupAttribute>

### <a name="attributes-for-test-methods"></a>Atributy pro testovací metody

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute>

## <a name="attributes-used-to-identify-test-classes-and-methods"></a>Atributy používané k identifikaci testovací třídy a metody

Každá třída test musí mít `TestClass` musí mít atribut a každou metodu test `TestMethod` atribut. Další informace najdete v tématu [anatomie testování částí](http://msdn.microsoft.com/a03d1ee7-9999-4e7c-85df-7d9073976144).

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>

## <a name="assert-classes-and-related-exceptions"></a>Assert – třídy a související výjimky

Testy jednotek můžete ověřit chování konkrétní aplikace jejich pomocí různé druhy kontrolní výrazy, výjimky a atributy. Další informace najdete v tématu [používání tříd Assert](../test/using-the-assert-classes.md).

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>

## <a name="the-testcontext-class"></a>TestContext – třída

V okně vlastností Visual Studio pro konkrétní testovací metodu se zobrazí následující atributy a hodnoty, které jsou jim přiřazeny. Tyto atributy se nepředpokládá, dostat kód testu jednotek. Místo toho ovlivňují způsobů, jak je testování částí použít nebo spouštět, které jste prostřednictvím IDE Visual Studio nebo modul testu sady Visual Studio. Například některé z těchto atributů zobrazit jako sloupce **Test Manager** okno a **výsledky testu** okna, což znamená, že můžete je použít k skupiny a řazení testy a výsledky testu. Jeden takový atribut je <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute>, které můžete přidat libovolný metadata do testování částí. Například může použít k uložení názvu průchodu testu, který obsahuje tento test pomocí označení jednotky testování s `[TestProperty("TestPass", "Accessibility")]`. Nebo, můžete ji použít k uložení slouží jako ukazatel druh testu s `[TestProperty("TestKind", "Localization")]`. Obě vlastnost vytvoříte pomocí tohoto atributu a hodnotu vlastnosti, které jsou přiřazeny, jsou zobrazeny v sadě Visual Studio **vlastnosti** okno pod nadpisem **konkrétní Test**.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.OwnerAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DeploymentItemAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DescriptionAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.IgnoreAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.WorkItemAttribute>

## <a name="test-configuration-classes"></a>Třídy konfigurace testu

- <xref:Microsoft.TeamFoundation.TestManagement.Client.ObjectTypes>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection>

## <a name="attributes-used-to-generate-reports"></a>Atributy sloužící ke generování sestav

Atributy v této části se týkají testovací metody, která budou uspořádání entit v hierarchii projektu týmového projektu pro Team Foundation Server.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CssIterationAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CssProjectStructureAttribute>

## <a name="classes-used-with-private-accessors"></a>Třídy používané s privátní přístupové objekty

Testování částí pro soukromá metoda můžete vygenerovat. Generování vytvoří třídu privátní přistupujícího objektu, který vytvoří instanci objektu <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject> třídy. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject> Třída představuje obálkovou třídu používající reflexe jako součást procesu privátní přistupujícího objektu. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateType> Třída je podobný, ale slouží pro volání privátní statické metody namísto volání metody privátní instance.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateType>

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting> referenční dokumentace
