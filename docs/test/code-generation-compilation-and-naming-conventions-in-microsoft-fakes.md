---
title: Generování kódu, kompilace a konvence pojmenování ve Fakes Microsoft pro sadu Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 93aec7e83ba5af9bab8da351624df861b46e475c
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282103"
---
# <a name="code-generation-compilation-and-naming-conventions-in-microsoft-fakes"></a>Vytváření, kompilace a konvence pojmenování kódu v Napodobeniny Microsoft

Tento článek popisuje možnosti a problémy v generování kódu v napodobeniny a kompilace a popisuje konvence pro typy Fakes generované, členů a parametry.

**Požadavky**

-   Visual Studio Enterprise
-   Rozhraní .NET Framework projektu

> [!NOTE]
> .NET standard projekty nejsou podporované.

## <a name="code-generation-and-compilation"></a>Vytváření a kompilování kódu

### <a name="configure-code-generation-of-stubs"></a>Konfigurovat kód generování zástupných procedur

Generování zástupných procedur typy je nakonfigurovaný v souboru XML, který má *.fakes* příponu souboru. Rozhraní framework Fakes integruje v procesu sestavení pomocí vlastní úlohy nástroje MSBuild a zjistí těchto souborů v čase vytvoření buildu. Generátor kódu Fakes kompilovaný typy se zakázaným inzerováním do sestavení a přidá odkaz na projekt.

Následující příklad ilustruje se zakázaným inzerováním typy definované v *FileSystem.dll*:

```xml
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">
    <Assembly Name="FileSystem"/>
</Fakes>
```

### <a name="type-filtering"></a>Filtrování typů

Filtry lze nastavit v *.fakes* souboru omezit, které typy by měla být prázdná. Můžete přidat bez vazby počet zaškrtnutí, přidat, odebrat elementů v rámci elementu StubGeneration na seznam vybraných typů.

Například následující *.fakes* soubor generuje zástupných procedur pro typy v oborech názvů systému a System.IO, ale nezahrnuje žádný typ, který obsahuje "Zpracování" v systému:

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

     `el` odpovídá "text hello"

-   Přidání `!` na konec filtr je přesné shody malá a velká písmena:

     `el!` neodpovídá "text hello"

     `hello!` odpovídá "text hello"

-   Přidání `*` na konec filtr umožňuje odpovídat předpona řetězce:

     `el*` neodpovídá "text hello"

     `he*` odpovídá "text hello"

-   Více filtrů v seznamu oddělených středníkem jsou spojeny jako disjunkce:

     `el;wo` odpovídá "text hello" a "world"

### <a name="stub-concrete-classes-and-virtual-methods"></a>Konkrétní třídy se zakázaným inzerováním a virtuální metody

Ve výchozím nastavení se zakázaným inzerováním typy jsou generovány pro všechny třídy, není zapečetěná. Je možné, abyste omezili typy se zakázaným inzerováním na abstraktní třídy prostřednictvím *.fakes* konfigurační soubor:

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

### <a name="internal-types"></a>Vnitřní typy

Generátor kódu Fakes generuje shim typy a typy se zakázaným inzerováním pro typy, které jsou viditelné pro generovaný sestavení Fakes. Ke zviditelnění interní typy shimmed sestavení Fakes a vaše testovací sestavení, přidejte <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atributy pro shimmed sestavení kód, který nabízí přehled vygenerované Fakes sestavení a testů sestavení. Tady je příklad:

```csharp
// FileSystem\AssemblyInfo.cs
[assembly: InternalsVisibleTo("FileSystem.Fakes")]
[assembly: InternalsVisibleTo("FileSystem.Tests")]
```

 **Vnitřní typy v sestavení se silným názvem**

 Pokud shimmed sestavení silným názvem, a chcete pro přístup k interní typy sestavení:

-   Vaše testovací sestavení a Fakes sestavení musí mít silné názvy.

-   Přidat test a Fakes sestavení do veřejných klíčů **InternalsVisibleToAttribute** atributů v shimmed sestavení. Tady je příklad atributy v kódu shimmed sestavení by vzhledu při shimmed sestavení silným názvem:

    ```csharp
    // FileSystem\AssemblyInfo.cs
    [assembly: InternalsVisibleTo("FileSystem.Fakes",
        PublicKey=<Fakes_assembly_public_key>)]
    [assembly: InternalsVisibleTo("FileSystem.Tests",
        PublicKey=<Test_assembly_public_key>)]
    ```

Pokud shimmed sestavení silným názvem, rozhraní Fakes automaticky důrazně podepisuje vygenerované sestavení Fakes. Budete muset silné podepsání sestavení testu. V tématu [sestavení se silným názvem](/dotnet/framework/app-domains/strong-named-assemblies).

Rozhraní framework Fakes používá stejný klíč k podepsání všechny generované sestavení, aby tento fragment kódu můžete použít jako počáteční bod přidat **InternalsVisibleTo** atribut pro sestavení fakes shimmed sestavení kódu.

```csharp
[assembly: InternalsVisibleTo("FileSystem.Fakes, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e92decb949446f688ab9f6973436c535bf50acd1fd580495aae3f875aa4e4f663ca77908c63b7f0996977cb98fcfdb35e05aa2c842002703cad835473caac5ef14107e3a7fae01120a96558785f48319f66daabc862872b2c53f5ac11fa335c0165e202b4c011334c7bc8f4c4e570cf255190f4e3e2cbc9137ca57cb687947bc")]
```

Například klíč jste vytvořili pro shimmed sestavení, zadejte úplnou cestu k, můžete zadat jiný veřejný klíč pro sestavení Fakes *.snk* soubor, který obsahuje alternativní klíč jako `KeyFile` hodnotu v atributu `Fakes` \\ `Compilation` element *.fakes* souboru. Příklad:

```xml
<-- FileSystem.Fakes.fakes -->
<Fakes ...>
  <Compilation KeyFile="full_path_to_the_alternate_snk_file" />
</Fakes>
```

Pak budete muset použít veřejný klíč alternativní *.snk* souboru jako druhý parametr atributu InternalVisibleTo Fakes sestavení v kódu shimmed sestavení:

```csharp
// FileSystem\AssemblyInfo.cs
[assembly: InternalsVisibleTo("FileSystem.Fakes",
    PublicKey=<Alternate_public_key>)]
[assembly: InternalsVisibleTo("FileSystem.Tests",
    PublicKey=<Test_assembly_public_key>)]
```

V příkladu výše, hodnoty `Alternate_public_key` a `Test_assembly_public_key` může být stejné.

### <a name="optimize-build-times"></a>Optimalizace sestavení časy

Kompilace sestavení Fakes může výrazně zvýšit vaši čase vytvoření buildu. Můžete minimalizovat čas sestavení vygenerováním Fakes sestavení pro sestavení .NET systému a sestavení třetích stran v samostatných centralizované projektu. Protože takové sestavení zřídka změnit na počítači, můžete opakovaně použít generovaného Fakes sestavení v jiné projekty.

Z vaší projektů testování částí přidáte odkaz na kompilované Fakes sestavení, které jsou umístěny v části FakesAssemblies ve složce projektu.

1.  Vytvořte nové knihovny tříd s verze rozhraní .NET runtime odpovídající testovací projekty. Umožňuje volání Fakes.Prebuild. Odeberte *class1.cs* souboru z projektu, není potřeba.

2.  Přidáte odkaz na systém a sestavení třetích stran, které potřebujete Fakes pro.

3.  Přidat *.fakes* soubor pro každou z těchto sestavení a sestavení.

4.  Z testovacího projektu

    -   Ujistěte se, že máte odkaz na knihovnu DLL modulu runtime Fakes:

         *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PublicAssemblies\Microsoft.QualityTools.Testing.Fakes.dll*

    -   Pro každé sestavení, který jste vytvořili Fakes pro, přidat odkaz na odpovídající soubor knihovny DLL v *Fakes.Prebuild\FakesAssemblies* složky vašeho projektu.

### <a name="avoid-assembly-name-clashing"></a>Vyhněte se s konfliktními název sestavení

V prostředí Team Build jsou sloučit všechny výstupy sestavení do jednoho adresáře. Pokud více projektů pomocí zástupného rozhraní, může dojít, Fakes sestavení z různých verzí přepsat navzájem. Například TestProject1 fakes *mscorlib.dll* z rozhraní .NET Framework 2.0 a TestProject2 fakes *mscorlib.dll* pro rozhraní .NET Framework 4 obě povede k *mscorlib. Fakes.dll* Fakes sestavení.

 K tomuto problému vyhnout, Fakes automaticky vytvořila názvy sestavení Fakes verze kvalifikovaný pro odkazy na jiný projekt při přidávání *.fakes* soubory. Verze kvalifikovaný název sestavení Fakes vloží číslo verze, když vytvoříte Fakes název sestavení:

 Zadaný MyAssembly sestavení a verze 1.2.3.4 je název sestavení Fakes MyAssembly.1.2.3.4.Fakes.

 Můžete změnit nebo odebrat tuto verzi a to úpravou atribut verze v elementu sestavení *.fakes*:

```xml
attribute of the Assembly element in the .fakes:
<Fakes ...>
  <Assembly Name="MyAssembly" Version="1.2.3.4" />
  ...
</Fakes>
```

## <a name="fakes-naming-conventions"></a>Fakes konvence vytváření názvů

### <a name="shim-type-and-stub-type-naming-conventions"></a>Shim typu a se zakázaným inzerováním zadejte zásady vytváření názvů

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

### <a name="shim-delegate-property-or-stub-delegate-field-naming-conventions"></a>Shim vlastnost nebo se zakázaným inzerováním delegáta pole delegáta konvence vytváření názvů

**Základní pravidla** pro pole názvy, od prázdný název:

-   Název metody je připojen.

-   Pokud název metody je explicitní implementace rozhraní, se odeberou se tečkami.

-   Pokud je metoda obecnou nebo `Of` *n* se připojí kde *n* je počet argumentů obecná metoda.

 **Názvy speciální metoda** jako je například vlastnost getter a setter, se považují jak je popsáno v následující tabulce:

|Pokud je metoda...|Příklad|Název metody připojeno|
|-------------------|-------------|--------------------------|
|A **– konstruktor**|`.ctor`|`Constructor`|
|Statického **– konstruktor**|`.cctor`|`StaticConstructor`|
|**Přistupujícího objektu** s metodou název skládá ze dvou částí oddělených "_" (například metody getter vlastnosti)|*kind_name* (běžné případu, ale nejsou vynucené podle ECMA)|*NameKind*, kde obě části byly velkými písmeny a prohodily|
||Metoda getter vlastnosti `Prop`|`PropGet`|
||Metoda setter vlastnosti `Prop`|`PropSet`|
||Přidávání událostí|`Add`|
||Nástroje pro odebrání události|`Remove`|
|**Operátor** skládá ze dvou částí|`op_name`|`NameOp`|
|Například: + – operátor|`op_Add`|`AddOp`|
|Pro **operátor převodu**, návratový typ se připojí.|`T op_Implicit`|`ImplicitOpT`|

> [!NOTE]
> - **Mechanismy získání a nastavení indexery** jsou zpracovávány podobně pro vlastnost. Výchozí název indexeru je `Item`.
> - **Typ parametru** názvy jsou transformovat a zřetězených.
> - **Návratový typ** se ignoruje, pokud je to nejednoznačnost přetížení. Pokud dojde přetížení amiguity, připojí se návratový typ na konci názvu.

### <a name="parameter-type-naming-conventions"></a>Parametr typu zásady vytváření názvů

|Zadané|Řetězec připojení je...|
|-----------|-------------------------|
|A **typu**`T`|T<br /><br /> Obor názvů, vnořené struktury a obecné énka jsou vyřadit.|
|**Vnější parametr**`out T`|`TOut`|
|A **parametr ref** `ref T`|`TRef`|
|**Pole typu**`T[]`|`TArray`|
|A **vícerozměrné** typu `T[ , , ]`|`T3`|
|A **ukazatel** typu `T*`|`TPtr`|
|A **obecného typu**`T<R1, ...>`|`TOfR1`|
|A **argument obecného typu** `!i` typu `C<TType>`|`Ti`|
|A **obecná metoda argument** `!!i` metody `M<MMethod>`|`Mi`|
|A **vnořené typu**`N.T`|`N` se připojí, pak `T`|

### <a name="recursive-rules"></a>Rekurzivní pravidla

Následující pravidla jsou rekurzivně:

-   Protože Fakes používá C# k vygenerování Fakes sestavení, je uvozena libovolný znak, který byste mohli vytvořit neplatný token C# k "_" (podtržítko).

-   Pokud výsledný název je v konfliktu s kteréhokoli člena deklarující typ, použije se schéma číslování připojením letopočty čítač, začínající od 01.

## <a name="see-also"></a>Viz také:

- [Izolace testovaného kódu pomocí Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md)
