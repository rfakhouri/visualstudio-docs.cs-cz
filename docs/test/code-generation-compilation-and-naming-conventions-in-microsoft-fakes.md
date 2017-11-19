---
title: "Vytváření, kompilace a konvence pojmenování ve Microsoft Fakes kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20221de4-2a9e-4787-b99a-b5855bb90872
caps.latest.revision: "16"
ms.author: douge
manager: douge
ms.openlocfilehash: 34cfe9041a9e724136c9d7c5a19b1c74f2309b2a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="code-generation-compilation-and-naming-conventions-in-microsoft-fakes"></a>Vytváření, kompilace a konvence pojmenování kódu v Napodobeniny Microsoft
Toto téma popisuje možnosti a problémy v generování kódu v napodobeniny a kompilace a popisuje konvence pro typy Fakes generované, členů a parametry.  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
##  <a name="BKMK_In_this_topic"></a>V tomto tématu  
  
-   [Vytváření a kompilování kódu](#BKMK_Code_generation_and_compilation)  
  
-   [Konfigurace kódu generování zástupných procedur](#BKMK_Configuring_code_generation_of_stubs)
  
-   [Filtrování typů](#BKMK_Type_filtering)
  
-   [Stubbing konkrétní třídy a metody virtuální](#BKMK_Stubbing_concrete_classes_and_virtual_methods)
  
-   [Vnitřní typy](#BKMK_Internal_types)
  
-   [Optimalizace sestavení časy](#BKMK_Optimizing_build_times)
  
-   [Zamezení s konfliktními název sestavení](#BKMK_Avoiding_assembly_name_clashing)  
  
-   [Fakes konvence vytváření názvů](#BKMK_Fakes_naming_conventions)  
  
-   [Shim typu a se zakázaným inzerováním zadejte zásady vytváření názvů](#BKMK_Shim_type_and_stub_type_naming_conventions)
  
-   [Shim vlastnost nebo se zakázaným inzerováním delegáta pole delegáta konvence vytváření názvů](#BKMK_Shim_delegate_property_or_stub_delegate_field_naming_conventions)
  
-   [Parametr typu zásady vytváření názvů](#BKMK_Parameter_type_naming_conventions)
  
-   [Rekurzivní pravidla](#BKMK_Recursive_rules)  
  
-   [Externí zdroje](#BKMK_External_resources)  
  
-   [Pokyny](#BKMK_Guidance)  
  
##  <a name="BKMK_Code_generation_and_compilation"></a>Vytváření a kompilování kódu  
  
###  <a name="BKMK_Configuring_code_generation_of_stubs"></a>Konfigurace kódu generování zástupných procedur  
 Generování zástupných procedur typy je nakonfigurován v souboru XML, který má příponu souboru .fakes. Rozhraní framework Fakes integruje v procesu sestavení pomocí vlastní úlohy nástroje MSBuild a zjistí těchto souborů v čase vytvoření buildu. Generátor kódu Fakes kompilovaný typy se zakázaným inzerováním do sestavení a přidá odkaz na projekt.  
  
 Následující příklad ilustruje se zakázaným inzerováním typy definované v FileSystem.dll:  
  
```xml  
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">  
    <Assembly Name="FileSystem"/>  
</Fakes>  
  
```  
  
###  <a name="BKMK_Type_filtering"></a>Filtrování typů  
 Filtry lze nastavit v souboru .fakes omezit, které typy by měla být prázdná. Můžete přidat bez vazby počet zaškrtnutí, přidat, odebrat elementů v rámci elementu StubGeneration na seznam vybraných typů.  
  
 Například tento soubor .fakes generuje zástupných procedur pro typy v oborech názvů systému a System.IO, ale nezahrnuje žádný typ, který obsahuje "Zpracování" v systému:  
  
```xml  
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">  
  <Assembly Name="mscorlib" />  
  <!-- user code -->  
  <StubGeneration>  
    <Clear />  
    <Add Namespace="System!" />  
    <Add Namespace="System.IO!"/>  
    <Remove TypeName="Handle" />  
  </StubGeneration>  
  <!-- /user code -->  
</Fakes>  
```  
  
 Řetězcích filtrů definovat, jak shody by mělo být provedeno pomocí jednoduché gramatika:  
  
-   Filtry, nerozlišují se ve výchozím nastavení; filtry provést porovnávání podřetězců:  
  
     `el`odpovídá "text hello"  
  
-   Přidání `!` na konec filtr znamená, že přesné shody malá a velká písmena:  
  
     `el!`neodpovídá "text hello"  
  
     `hello!`odpovídá "text hello"  
  
-   Přidání `*` na konec filtr bude odpovídat předpona řetězce:  
  
     `el*`neodpovídá "text hello"  
  
     `he*`odpovídá "text hello"  
  
-   Více filtrů v seznamu oddělených středníkem jsou spojeny jako disjunkce:  
  
     `el;wo`odpovídá "text hello" a "world"  
  
###  <a name="BKMK_Stubbing_concrete_classes_and_virtual_methods"></a>Stubbing konkrétní třídy a metody virtuální  
 Ve výchozím nastavení se zakázaným inzerováním typy jsou generovány pro všechny třídy, není zapečetěná. Je možné omezit se zakázaným inzerováním typy, které mají abstraktní třídy pomocí konfiguračního souboru .fakes:  
  
```xml  
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">  
  <Assembly Name="mscorlib" />  
  <!-- user code -->  
  <StubGeneration>  
    <Types>  
      <Clear />  
      <Add AbstractClasses="true"/>  
    </Types>  
  </StubGeneration>  
  <!-- /user code -->  
</Fakes>  
```  
  
###  <a name="BKMK_Internal_types"></a>Vnitřní typy  
 Generátor kódu Fakes bude generovat shim typy a zóny se zakázaným inzerováním pro typy, které jsou viditelné pro generovaný sestavení Fakes. Ke zviditelnění interní typy shimmed sestavení Fakes a vaše testovací sestavení, přidejte <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atributy pro shimmed sestavení kód, který nabízí přehled vygenerované Fakes sestavení a testů sestavení. Tady je příklad:  
  
```csharp  
// FileSystem\AssemblyInfo.cs  
[assembly: InternalsVisibleTo("FileSystem.Fakes")]  
[assembly: InternalsVisibleTo("FileSystem.Tests")]  
```  
  
 **Vnitřní typy v sestavení se silným názvem**  
  
 Pokud shimmed sestavení silným názvem a chcete, aby interní typy přístupu sestavení:  
  
-   Vaše testovací sestavení a Fakes sestavení musí mít silné názvy.  
  
-   Je nutné přidat test a Fakes sestavení do veřejných klíčů **InternalsVisibleToAttribute** atributů v shimmed sestavení. Tady je vzhledu náš příklad atributů v kódu shimmed sestavení při shimmed sestavení silným názvem:  
  
    ```csharp  
    // FileSystem\AssemblyInfo.cs  
    [assembly: InternalsVisibleTo("FileSystem.Fakes",  
        PublicKey=<Fakes_assembly_public_key>)]  
    [assembly: InternalsVisibleTo("FileSystem.Tests",  
        PublicKey=<Test_assembly_public_key>)]  
    ```  
  
 Pokud shimmed sestavení silným názvem, rozhraní Fakes podepíše automaticky důrazně vygenerované sestavení Fakes. Budete muset silné podepsání sestavení testu. V tématu [vytváření a používání sestavení se silným názvem](http://msdn.microsoft.com/Library/ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9).  
  
 Rozhraní framework Fakes používá stejný klíč k podepsání všechny generované sestavení, aby tento fragment kódu můžete použít jako počáteční bod přidat **InternalsVisibleTo** atribut pro sestavení fakes shimmed sestavení kódu.  
  
```csharp  
[assembly: InternalsVisibleTo("FileSystem.Fakes, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e92decb949446f688ab9f6973436c535bf50acd1fd580495aae3f875aa4e4f663ca77908c63b7f0996977cb98fcfdb35e05aa2c842002703cad835473caac5ef14107e3a7fae01120a96558785f48319f66daabc862872b2c53f5ac11fa335c0165e202b4c011334c7bc8f4c4e570cf255190f4e3e2cbc9137ca57cb687947bc")]  
```  
  
 Například klíč jste vytvořili pro shimmed sestavení, zadejte úplnou cestu k, můžete zadat jiný veřejný klíč pro sestavení Fakes **.snk** soubor, který obsahuje alternativní klíč jako `KeyFile` hodnotu v atributu `Fakes` \\ `Compilation` element **.fakes** souboru. Příklad:  
  
```xml  
<-- FileSystem.Fakes.fakes -->  
<Fakes ...>  
  <Compilation KeyFile="full_path_to_the_alternate_snk_file" />  
</Fakes>  
  
```  
  
 Pak budete muset použít veřejný klíč alternativní **.snk** souboru jako druhý parametr atributu InternalVisibleTo Fakes sestavení v kódu shimmed sestavení:  
  
```csharp  
// FileSystem\AssemblyInfo.cs  
[assembly: InternalsVisibleTo("FileSystem.Fakes",  
    PublicKey=<Alternate_public_key>)]  
[assembly: InternalsVisibleTo("FileSystem.Tests",  
    PublicKey=<Test_assembly_public_key>)]  
```  
  
 V příkladu výše, hodnoty `Alternate_public_key` a `Test_assembly_public_key` může být stejné.  
  
###  <a name="BKMK_Optimizing_build_times"></a>Optimalizace sestavení časy  
 Kompilace sestavení Fakes může výrazně zvýšit vaši čase vytvoření buildu. Můžete minimalizovat čas sestavení vygenerováním Fakes sestavení pro sestavení .NET systému a sestavení třetích stran v samostatných centralizované projektu. Protože takové sestavení zřídka změnit na počítači, můžete opakovaně použít generovaného Fakes sestavení v jiné projekty.  
  
 Z vaší projektů testů jednotek můžete jednoduše provést odkaz na kompilované Fakes sestavení, které jsou umístěny v části FakesAssemblies ve složce projektu.  
  
1.  Vytvořte nové knihovny tříd s verze rozhraní .NET runtime odpovídající testovací projekty. Umožňuje volání Fakes.Prebuild. Odstraňte soubor class1.cs z projektu, není potřeba.  
  
2.  Přidáte odkaz na systém a sestavení třetích stran, které potřebujete Fakes pro.  
  
3.  Přidejte soubor .fakes pro každou z těchto sestavení a sestavení.  
  
4.  Z testovacího projektu  
  
    -   Ujistěte se, že máte odkaz na knihovnu DLL modulu runtime Fakes:  
  
         C:\Program Files\Microsoft 12.0\Common7\IDE\PublicAssemblies\Microsoft.QualityTools.Testing.Fakes.dll sady Visual Studio  
  
    -   Pro každé sestavení, které jste vytvořili Fakes pro, přidejte odkaz na odpovídající soubor knihovny DLL ve složce Fakes.Prebuild\FakesAssemblies projektu.  
  
###  <a name="BKMK_Avoiding_assembly_name_clashing"></a>Zamezení s konfliktními název sestavení  
 V prostředí Team Build jsou sloučit všechny výstupy sestavení do jednoho adresáře. V případě více projektů pomocí zástupného rozhraní může dojít, Fakes sestavení z jiné verze přepsat navzájem. Například TestProject1 fakes mscorlib.dll z rozhraní .NET Framework 2.0 a TestProject2 fakes mscorlib.dll pro rozhraní .NET Framework 4 by yield na mscorlib. Sestavení Fakes.dll Fakes.  
  
 K tomuto problému vyhnout, by měl Fakes automaticky vytvoří verzi kvalifikovaný Fakes názvy sestavení pro odkazy na jiný projekt, při přidávání souborů .fakes. Verze kvalifikovaný název sestavení Fakes vloží číslo verze, když vytvoříte Fakes název sestavení:  
  
 Zadaný MyAssembly sestavení a verze 1.2.3.4 je název sestavení Fakes MyAssembly.1.2.3.4.Fakes.  
  
 Můžete změnit nebo odebrat tuto verzi a to úpravou atribut verze elementu sestavení v .fakes:  
  
```xml  
attribute of the Assembly element in the .fakes:  
<Fakes ...>  
  <Assembly Name="MyAssembly" Version="1.2.3.4" />  
  ...  
</Fakes>  
  
```  
  
##  <a name="BKMK_Fakes_naming_conventions"></a>Fakes konvence vytváření názvů  
  
###  <a name="BKMK_Shim_type_and_stub_type_naming_conventions"></a>Shim typu a se zakázaným inzerováním zadejte zásady vytváření názvů  
 **Obory názvů**  
  
-   . Přidá do oboru názvů přípona fakes.  
  
     Například `System.Fakes` obor názvů obsahuje typy shim System – obor názvů.  
  
-   Global.Fakes obsahuje shim typ prázdný oboru názvů.  
  
 **Názvy typů**  
  
-   Předponou Shim se přidá k názvu typu sestavení shim název typu.  
  
     Například ShimExample je typ shim příklad typu.  
  
-   Předpona se zakázaným inzerováním se přidá k názvu typu vytvořit se zakázaným inzerováním název typu.  
  
     Například StubIExample je typ se zakázaným inzerováním IExample typu.  
  
 **Argumenty typu a struktury vnořené typy**  
  
-   Zkopírují se argumenty obecného typu.  
  
-   Vnořené typy struktura zkopírován pro typy shim.  
  
###  <a name="BKMK_Shim_delegate_property_or_stub_delegate_field_naming_conventions"></a>Shim vlastnost nebo se zakázaným inzerováním delegáta pole delegáta konvence vytváření názvů  
 **Základní pravidla** pro pole názvy, od prázdný název:  
  
-   Název metody je připojen.  
  
-   Pokud název metody je explicitní implementace rozhraní, se odeberou se tečkami.  
  
-   Pokud je metoda obecnou nebo `Of`  *n*  se připojí kde  *n*  je počet argumentů obecná metoda.  
  
 **Názvy speciální metoda** jako je například vlastnost getter a setter, se považují jak je popsáno v následující tabulce.  
  
|Pokud je metoda...|Příklad|Název metody připojeno|  
|-------------------|-------------|--------------------------|  
|A **– konstruktor**|`.ctor`|`Constructor`|  
|Statického **– konstruktor**|`.cctor`|`StaticConstructor`|  
|**Přistupujícího objektu** s metodou název skládá ze dvou částí oddělených "_" (například metody getter vlastnosti)|*kind_name* (běžné případu, ale nejsou vynucené podle ECMA)|*NameKind*, kde obě části byly velkými písmeny a prohodily|  
||Metoda getter vlastnosti`Prop`|`PropGet`|  
||Metoda setter vlastnosti`Prop`|`PropSet`|  
||Přidávání událostí|`Add`|  
||Nástroje pro odebrání události|`Remove`|  
|**Operátor** skládá ze dvou částí|`op_name`|`NameOp`|  
|Například: + – operátor|`op_Add`|`AddOp`|  
|Pro **operátor převodu**, návratový typ se připojí.|`T op_Implicit`|`ImplicitOpT`|  
  
 **Poznámky**  
  
-   **Mechanismy získání a nastavení indexery** jsou zpracovávány podobně pro vlastnost. Výchozí název indexeru je `Item`.  
  
-   **Typ parametru** názvy jsou transformovat a zřetězených.  
  
-   **Návratový typ** se ignoruje, pokud je to nejednoznačnost přetížení. Pokud je to tento případ, návratový typ je přidán na konec názvu  
  
###  <a name="BKMK_Parameter_type_naming_conventions"></a>Parametr typu zásady vytváření názvů  
  
|Zadané|Řetězec připojení je...|  
|-----------|-------------------------|  
|A **typu**`T`|T<br /><br /> Obor názvů, vnořené struktury a obecné énka jsou vyřadit.|  
|**Vnější parametr**`out T`|`TOut`|  
|A **parametr ref**`ref T`|`TRef`|  
|**Pole typu**`T[]`|`TArray`|  
|A **vícerozměrné** typu`T[ , , ]`|`T3`|  
|A **ukazatel** typu`T*`|`TPtr`|  
|A **obecného typu**`T<R1, ...>`|`TOfR1`|  
|A **argument obecného typu** `!i` typu`C<TType>`|`Ti`|  
|A **obecná metoda argument** `!!i` metody`M<MMethod>`|`Mi`|  
|A **vnořené typu**`N.T`|`N`se připojí, pak`T`|  
  
###  <a name="BKMK_Recursive_rules"></a>Rekurzivní pravidla  
 Následující pravidla jsou rekurzivně:  
  
-   Protože Fakes používá C# k vygenerování Fakes sestavení, je uvozena libovolný znak, který byste mohli vytvořit neplatný token C# k "_" (podtržítko).  
  
-   Pokud výsledný název je v konfliktu s kteréhokoli člena deklarující typ, použije se schéma číslování připojením letopočty čítač, začínající od 01.  
  
##  <a name="BKMK_External_resources"></a>Externí zdroje  
  
###  <a name="BKMK_Guidance"></a>Pokyny  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 2: testování částí: testování uvnitř](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
## <a name="see-also"></a>Viz také  
 [Izolace testovaného kódu pomocí zástupného rozhraní Microsoft](../test/isolating-code-under-test-with-microsoft-fakes.md)
