---
title: "Používání členů oboru názvů Microsoft.VisualStudio.TestTools.UnitTesting při testování částí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fa335fd-e442-448f-913f-25a19df90a93
caps.latest.revision: "6"
ms.author: douge
manager: douge
ms.openlocfilehash: 1a723104cdd350dcc2c5fac80eef4e98b178df4c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="using-microsoftvisualstudiotesttoolsunittesting-members-in-unit-tests"></a>Používání členů oboru názvů Microsoft.VisualStudio.TestTools.UnitTesting při testech jednotek
Unit Testing Framework podporuje testování v částí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Používání tříd a členy v Microsoft.VisualStudio.TestPlatform.UnitTestFramework > obor názvů při programování testování částí. Můžete je používat, když jste napsali jednotka testů od začátku, nebo jsou upřesnění testů jednotek, která byla vygenerována z kódu, který testujete.  
  
## <a name="groups-of-elements"></a>Skupiny elementů  
 V této části pomáhají jasnější přehled Unit Testing Framework, organizuje elementy UnitTesting oboru názvů do skupin souvisejících funkcí.  
  
> [!NOTE]
>  Atribut elementy, jejichž názvy dokončete řetězcem atribut, lze s nebo bez řetězec atributu. Například následující příklady kódu dvě pracovat stejně jako:  
>   
>  `[TestClass()]`  
>   
>  `[TestClassAttribute()]`  
  
### <a name="elements-used-for-data-driven-testing"></a>Prvky používané pro datové testování  
 Nastavit testy jednotek řízené daty pomocí následující prvky. Další informace najdete v tématu [postupy: vytvoření testů jednotek Data-Driven](../test/how-to-create-a-data-driven-unit-test.md) a [návod: použití konfiguračního souboru k definování zdroje dat](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md).  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataAccessMethod  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataSourceAttribute 
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataSourceElement  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataSourceElementCollection  
  
## <a name="attributes-used-to-establish-a-calling-order"></a>Atributy se používají ke zřízení pořadí volání  
 Element kódu dekorované s jedním z následujících atributů je volána v okamžiku, kdy je zadat. Další informace najdete v tématu [anatomie testování částí](http://msdn.microsoft.com/en-us/a03d1ee7-9999-4e7c-85df-7d9073976144).  
  
### <a name="for-assemblies"></a>Pro sestavení  
 AssemblyInitialize a AssemblyCleanup se nazývají práva po načtení vaše sestavení a pravé před uvolněním vaše sestavení.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssemblyInitializeAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssemblyCleanupAttribute  
  
### <a name="for-classes"></a>Pro třídy  
 ClassInitialize a ClassCleanup se nazývají práva po načtení třídě a pravé před uvolněním třídě.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.ClassInitializeAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.ClassCleanupAttribute  
  
### <a name="for-test-methods"></a>Pro testovací metody  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestInitializeAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestCleanupAttribute  
  
## <a name="attributes-used-to-identify-test-classes-and-methods"></a>Atributy používané k identifikaci testovací třídy a metody  
 Každá třída test musí mít atribut TestClass a každou metodu test musí mít atribut TestMethod. Další informace najdete v tématu [anatomie testování částí](http://msdn.microsoft.com/en-us/a03d1ee7-9999-4e7c-85df-7d9073976144).  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestClassAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestMethodAttribute  
  
## <a name="assert-classes-and-related-exceptions"></a>Assert – třídy a související výjimky  
 Testy jednotek můžete ověřit chování konkrétní aplikace jejich pomocí různé typy příkazů Assert, výjimky a atributy. Další informace najdete v tématu [používání tříd Assert](../test/using-the-assert-classes.md).  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.Assert 
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.CollectionAssert  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.StringAssert  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssertFailedException  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssertInconclusiveException  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.UnitTestAssertException  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.ExpectedExceptionAttribute  
  
## <a name="the-testcontext-class"></a>TestContext – třída  
 Následující atributy a hodnoty, které jsou jim přiřazeny se zobrazí v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vlastnosti – okno pro konkrétní testovací metodu. Tyto atributy se nepředpokládá, dostat kód testu jednotek. Místo toho budou mít vliv na způsoby, které slouží k testování částí nebo spustit, ať již prostřednictvím integrovaného vývojového prostředí z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], nebo pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] modul testu. Například některé z těchto atributů zobrazit jako sloupce v okně Test Manager a v okně Výsledky testu, to znamená, že můžete je použít k skupiny a řazení testy a výsledky testu. Jeden takový atribut je TestPropertyAttribute, které můžete přidat libovolný metadata do testování částí. Například může použít k uložení názvu průchodu testu, který obsahuje tento test pomocí označení jednotky testování s `[TestProperty("TestPass", "Accessibility")]`. Nebo můžete ji použít k uložení druh testu je slouží jako ukazatel: `[TestProperty("TestKind", "Localization")]`. Obě vlastnosti, které vytvoříte pomocí tohoto atributu a hodnota vlastnosti je přiřadit, jsou zobrazeny v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vlastnosti – okno pod nadpisem **konkrétní Test**.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.OwnerAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DeploymentItemAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DescriptionAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.HostTypeAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.IgnoreAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.PriorityAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestPropertyAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.WorkItemAttribute  
  
## <a name="test-configuration-classes"></a>Třídy konfigurace testu  
  
-   Microsoft.TeamFoundation.TestManagement.Client.ObjectTypes >  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestConfigurationSection  
  
## <a name="attributes-used-for-generating-reports"></a>Atributy používané pro generování sestav  
 Atributy v této části se týkají testovací metody, která budou uspořádání entit v hierarchii projektu [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] týmového projektu.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.CssIterationAttribute  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.CssProjectStructureAttribute  
  
## <a name="classes-used-with-private-accessors"></a>Třídy používané s privátní přístupové objekty  
 Jak je popsáno v [pomocí zveřejnit vytvoření přistupujícího objektu privátní](http://msdn.microsoft.com/en-us/2056c6a7-6672-42a7-8f53-fead33c56deb), můžete vygenerovat testů jednotek pro soukromá metoda. Generování vytvoří třídu privátní přístupového objektu, který vytvoří instanci objektu třídy PrivateObject. Třída PrivateObject je obálku třídu, která používá reflexe jako součást procesu privátní přistupujícího objektu. Třída PrivateType je podobný, ale slouží pro volání privátní statické metody namísto volání metody privátní instance.  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.PrivateObject  
  
-   Microsoft.VisualStudio.TestPlatform.UnitTestFramework.PrivateType  
  
## <a name="see-also"></a>Viz také  
 Microsoft.VisualStudio.TestPlatform.UnitTestFramework
