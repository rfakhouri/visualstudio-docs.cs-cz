---
title: 'Návod: Vytvoření souboru projektu MSBuild od začátku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, tutorial
ms.assetid: e3acff7c-cb4e-4ae1-8be2-a871bcff847b
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b01e917d0e46c6e5a5d91473332062a75ff1e33d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-an-msbuild-project-file-from-scratch"></a>Návod: Vytvoření souboru projektu MSBuild od začátku
Programovací jazyky, které cílí na rozhraní .NET Framework použijte soubory projektu nástroje MSBuild k označení a řízení procesu sestavení aplikace. Pokud používáte Visual Studio k vytvoření souboru projektu nástroje MSBuild, příslušné XML je automaticky přidá do souboru. Ale možná bude vhodné se seznámit s uspořádání XML a jak ji k řízení sestavení můžete změnit.  
  
 Informace o vytvoření souboru projektu pro projektu jazyka C++ najdete v tématu [MSBuild (Visual C++)](/cpp/build/msbuild-visual-cpp).  
  
 Tento návod ukazuje, jak vytvořit základní projekt soubor postupně, pomocí textového editoru. Průvodce zahrnuje následující kroky:  
  
-   Vytvoření zdrojového souboru minimální aplikace.  
  
-   Vytvořte minimální soubor projektu nástroje MSBuild.  
  
-   Proměnné prostředí PATH zahrnout MSBuild rozšiřte.  
  
-   Sestavení aplikace pomocí souboru projektu.  
  
-   Přidáte vlastnosti pro řízení sestavení.  
  
-   Ovládací prvek sestavení změnou hodnoty vlastnosti.  
  
-   Přidání cíle do sestavení.  
  
-   Ovládací prvek sestavení tak, že zadáte cíle.  
  
-   Přírůstkové sestavování.  
  
 Tento návod ukazuje, jak pro sestavení projektu na příkazovém řádku a podívejte se na výsledky. Další informace o MSBuild a jak spouštět nástroje MSBuild v příkazovém řádku najdete v tématu [návod: použití nástroje MSBuild](../msbuild/walkthrough-using-msbuild.md).  
  
 K dokončení průvodce, musíte mít rozhraní .NET Framework (verze 2.0, 3.5, 4.0 nebo 4.5) nainstalovat, protože obsahuje MSBuild a kompilátor Visual C#, které jsou potřebné pro průvodce.  
  
## <a name="creating-a-minimal-application"></a>Vytvoření minimální aplikace  
 Tato část ukazuje postup vytvoření minimální Visual C# aplikace zdrojového souboru pomocí textového editoru.  
  
#### <a name="to-create-the-minimal-application"></a>Chcete-li vytvořit minimální aplikace  
  
1.  Na příkazovém řádku přejděte do složky, kde chcete vytvořit aplikaci, například \My Documents\ nebo \Desktop\\.  
  
2.  Typ **md HelloWorld** vytvořit podsložku s názvem \HelloWorld\\.  
  
3.  Typ **cd HelloWorld** do nové složky.  
  
4.  Spusťte program Poznámkový blok nebo jiném textovém editoru a pak zadejte následující kód.  
  
    ```csharp
    using System;  
  
    class HelloWorld  
    {  
        static void Main()  
        {  
    #if DebugConfig  
            Console.WriteLine("WE ARE IN THE DEBUG CONFIGURATION");  
    #endif  
  
            Console.WriteLine("Hello, world!");  
        }  
    }  
    ```  
  
5.  Uložte tento soubor zdrojového kódu a pojmenujte ji Helloworld.cs.  
  
6.  Sestavení aplikace tak, že zadáte **csc helloworld.cs** na příkazovém řádku.  
  
7.  Testování aplikace tak, že zadáte **helloworld** na příkazovém řádku.  
  
     **Hello, world!** by se zobrazit zpráva.  
  
8.  Odstranit aplikaci tak, že zadáte **del helloworld.exe** na příkazovém řádku.  
  
## <a name="creating-a-minimal-msbuild-project-file"></a>Vytvoření souboru minimální projektu nástroje MSBuild  
 Teď, když máte zdrojového souboru minimální aplikace, můžete vytvořit soubor minimální projektu pro sestavení aplikace. Tento projektový soubor obsahuje následující prvky:  
  
-   Požadovaný kořenový `Project` uzlu.  
  
-   `ItemGroup` Uzlu tak, aby obsahovala elementy položky.  
  
-   Položka element, který odkazuje na zdrojový soubor aplikace.  
  
-   A `Target` uzlu tak, aby obsahovala úlohy, které jsou nutné k sestavení aplikace.  
  
-   A `Task` elementu, který chcete spustit kompilátor Visual C# k vytvoření aplikace.  
  
#### <a name="to-create-a-minimal-msbuild-project-file"></a>Chcete-li vytvořit minimální soubor projektu nástroje MSBuild  
  
1.  V textovém editoru nahradí existující text s použitím tyto dva řádky:  
  
    ```xml  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  Vložte tuto `ItemGroup` uzlu jako podřízeného prvku `Project` uzlu:  
  
    ```xml  
    <ItemGroup>  
      <Compile Include="helloworld.cs" />  
    </ItemGroup>  
    ```  
  
     Všimněte si které tento `ItemGroup` již obsahuje položku element.  
  
3.  Přidat `Target` uzlu jako podřízeného prvku `Project` uzlu. Název uzlu `Build`.  
  
    ```xml  
    <Target Name="Build">  
    </Target>  
    ```  
  
4.  Tento element úloh Vložit jako podřízený element `Target` uzlu:  
  
    ```xml  
    <Csc Sources="@(Compile)"/>  
    ```  
  
5.  Uložte tento soubor projektu s názvem Helloworld.csproj.  
  
 Soubor minimální projektu by měla vypadat přibližně následující kód:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <ItemGroup>  
    <Compile Include="helloworld.cs" />  
  </ItemGroup>  
  <Target Name="Build">  
    <Csc Sources="@(Compile)"/>    
  </Target>  
</Project>  
```  
  
 Úlohy v cíl sestavení jsou prováděny postupně. V tomto případě kompilátor Visual C# `Csc` úloha je pouze úlohy. Očekává, že seznam zdrojové soubory pro kompilaci a je dáno hodnotu `Compile` položky. `Compile` Položku odkazuje jenom jeden zdrojový soubor, Helloworld.cs.  
  
> [!NOTE]
>  V elementu položky můžete zástupný znak hvězdička (*) Chcete-li všechny soubory, které mají příponu názvu souboru .cs, následujícím způsobem:  
>   
>  `<Compile Include="*.cs" />`  
>   
>  Však není doporučeno použití zástupných znaků vzhledem k tomu, že umožňuje ladění a selektivní cílení obtížnější, pokud zdrojové soubory jsou přidány nebo odstraněny.  
  
## <a name="extending-the-path-to-include-msbuild"></a>Rozšíření cesty k zahrnují nástroje MSBuild  
 Než se dostanete k MSBuild, musíte rozšířit proměnné prostředí PATH na složku rozhraní .NET Framework.  
  
#### <a name="to-add-msbuild-to-your-path"></a>Chcete-li přidat MSBuild pro vaši cestu  
  
-   Spouštění v sadě Visual Studio 2013, můžete najít MSBuild.exe ve složce nástroje MSBuild (`%ProgramFiles%\MSBuild` na 32bitové verzi operačního systému, nebo `%ProgramFiles(x86)%\MSBuild` na 64bitový operační systém).  
  
     Na příkazovém řádku zadejte **nastavit PATH=%PATH%;%ProgramFiles%\MSBuild** nebo **nastavit CESTU k = % PATH %; % ProgramFiles (x86) %\MSBuild**.  
  
     Případně, pokud máte nainstalovanou sadu Visual Studio, můžete použít **Visual Studio – příkazový řádek**, který má cestu, která obsahuje složku nástroje MSBuild.  
  
## <a name="using-the-project-file-to-build-the-application"></a>Sestavení aplikace pomocí souboru projektu  
 Nyní sestavení aplikace, použijte soubor projektu, který jste právě vytvořili.  
  
#### <a name="to-build-the-application"></a>K vytvoření aplikace  
  
1.  Na příkazovém řádku zadejte **msbuild helloworld.csproj /t:Build**.  
  
     Toto sestavení cíl sestavení souboru projektu Helloworld vyvoláním kompilátor Visual C# k vytvoření aplikace Hello World.  
  
2.  Testování aplikace tak, že zadáte **helloworld**.  
  
     **Hello, world!** by se zobrazit zpráva.  
  
> [!NOTE]
>  Zobrazí se další podrobnosti o sestavení zvýšením úrovně podrobností. Nastavení úrovně podrobností na "podrobné", zadejte některý z těchto příkazů v příkazovém řádku příkaz:  
>   
>  **MSBuild helloworld.csproj /t:Build /verbosity: podrobné**  
  
## <a name="adding-build-properties"></a>Přidání vlastnosti sestavení  
 Vlastnosti sestavení můžete přidat do souboru projektu pro další ovládání sestavení. Nyní přidejte tyto vlastnosti:  
  
-   `AssemblyName` Vlastnosti k určení názvu aplikace.  
  
-   `OutputPath` Vlastnosti a určit složku obsahující aplikaci.  
  
#### <a name="to-add-build-properties"></a>K přidání vlastností sestavení  
  
1.  Odstranit existující aplikaci tak, že zadáte **del helloworld.exe** na příkazovém řádku.  
  
2.  V souboru projektu, vložte tuto `PropertyGroup` element právě po otevření `Project` element:  
  
    ```xml  
    <PropertyGroup>  
      <AssemblyName>MSBuildSample</AssemblyName>  
      <OutputPath>Bin\</OutputPath>  
    </PropertyGroup>  
    ```  
  
3.  Přidejte tuto úlohu na cíl sestavení těsně před `Csc` úloh:  
  
    ```xml  
    <MakeDir Directories="$(OutputPath)"      Condition="!Exists('$(OutputPath)')" />  
    ```  
  
     `MakeDir` Úloh vytvoří složku s názvem `OutputPath` vlastnost, zadat, že aktuálně neexistuje žádná složka s tímto názvem.  
  
4.  Přidejte tuto `OutputAssembly` atribut `Csc` úloh:  
  
    ```xml  
    <Csc Sources="@(Compile)" OutputAssembly="$(OutputPath)$(AssemblyName).exe" />  
    ```  
  
     To dává pokyn kompilátoru jazyka Visual C# k vytvoření sestavení s názvem `AssemblyName` vlastnost a umístí jej do složky s názvem `OutputPath` vlastnost.  
  
5.  Uložte provedené změny.  
  
 Soubor projektu by měl nyní vypadat následující kód:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <AssemblyName>MSBuildSample</AssemblyName>  
    <OutputPath>Bin\</OutputPath>  
  </PropertyGroup>  
  <ItemGroup>  
    <Compile Include="helloworld.cs" />  
  </ItemGroup>  
  <Target Name="Build">  
    <MakeDir Directories="$(OutputPath)" Condition="!Exists('$(OutputPath)')" />  
    <Csc Sources="@(Compile)" OutputAssembly="$(OutputPath)$(AssemblyName).exe" />  
  </Target>  
</Project>  
```  
  
> [!NOTE]
>  Doporučujeme, abyste přidali zpětné lomítko (\\) oddělovač cesty na konci názvu složky, když zadáte v `OutputPath` element nepřidávat ho `OutputAssembly` atribut `Csc` úloh. Proto  
>   
>  `<OutputPath>Bin\</OutputPath>`  
>   
>  `OutputAssembly=="$(OutputPath)$(AssemblyName).exe" />`  
>   
>  je lepší, než  
>   
>  `<OutputPath>Bin</OutputPath>`  
>   
>  `OutputAssembly=="$(OutputPath)\$(AssemblyName).exe" />`  
  
## <a name="testing-the-build-properties"></a>Testování vlastností sestavení  
 Nyní můžete sestavit aplikace pomocí souboru projektu, ve kterém jste použili sestavení vlastnosti k určení názvu výstupní složky a aplikace.  
  
#### <a name="to-test-the-build-properties"></a>K testování vlastnosti sestavení  
  
1.  Na příkazovém řádku zadejte **msbuild helloworld.csproj /t:Build**.  
  
     To vytvoří složku \Bin\ vyvolá kompilátor Visual C# k vytvoření aplikace MSBuildSample a umístí jej do složky \Bin\.  
  
2.  Chcete-li ověřit vytvořený složky \Bin\ a obsahuje MSBuildSample aplikace, zadejte **dir Bin**.  
  
3.  Testování aplikace tak, že zadáte **Bin\MSBuildSample**.  
  
     **Hello, world!** by se zobrazit zpráva.  
  
## <a name="adding-build-targets"></a>Přidání cíle sestavení  
 V dalším kroku přidejte dva další cíle soubor projektu, následujícím způsobem:  
  
-   Vyčištění cíl, který odstraní původní soubory.  
  
-   Opětovné sestavení cíl, který používá `DependsOnTargets` atribut vynutit čistou úloha pro spuštění před sestavovací úlohy.  
  
 Teď, když máte více cílů, můžete nastavit jako cíl výchozí cíl sestavení.  
  
#### <a name="to-add-build-targets"></a>Chcete-li přidat sestavení cílů  
  
1.  V souboru projektu přidejte hned za cíl sestavení tyto dva cíle:  
  
    ```xml  
    <Target Name="Clean" >  
      <Delete Files="$(OutputPath)$(AssemblyName).exe" />  
    </Target>  
    <Target Name="Rebuild" DependsOnTargets="Clean;Build" />  
    ```  
  
     Vyčištění cíl vyvolá úloha odstranění DELETE pro aplikaci. Opětovné sestavení cíl nejde spustit, dokud spustili čistou cíl a cíl sestavení. I když cíl opětovné sestavení neobsahuje žádné úkoly, způsobí čistou cíl, který má spustit před cíl sestavení.  
  
2.  Přidejte tuto `DefaultTargets` atribut otevření `Project` element:  
  
    ```xml  
    <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ```  
  
     Tento cíl sestavení nastaví jako výchozí cíl.  
  
 Soubor projektu by měl nyní vypadat následující kód:  
  
```xml  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <AssemblyName>MSBuildSample</AssemblyName>  
    <OutputPath>Bin\</OutputPath>  
  </PropertyGroup>  
  <ItemGroup>  
    <Compile Include="helloworld.cs" />  
  </ItemGroup>  
  <Target Name="Build">  
    <MakeDir Directories="$(OutputPath)" Condition="!Exists('$(OutputPath)')" />  
    <Csc Sources="@(Compile)" OutputAssembly="$(OutputPath)$(AssemblyName).exe" />  
  </Target>  
  <Target Name="Clean" >  
    <Delete Files="$(OutputPath)$(AssemblyName).exe" />  
  </Target>  
  <Target Name="Rebuild" DependsOnTargets="Clean;Build" />  
</Project>  
```  
  
## <a name="testing-the-build-targets"></a>Testování sestavení cílů  
 Mohou vykonávat nového cíle sestavení k otestování tyto funkce souboru projektu:  
  
-   Vytváření sestavení výchozí.  
  
-   Nastavení názvu aplikace, na příkazovém řádku.  
  
-   Odstranění aplikace předtím, než je vytvořen jinou aplikací.  
  
-   Odstranění aplikace bez vytváření jiná aplikace.  
  
#### <a name="to-test-the-build-targets"></a>Pro testování sestavení cílů  
  
1.  Na příkazovém řádku zadejte **msbuild helloworld.csproj /p:AssemblyName = pozdrav**.  
  
     Protože jste nepoužili **/t** přepnout explicitně nastavit cíl, MSBuild spustí výchozí cíl sestavení. **/P** přepínač přepsání `AssemblyName` vlastnost a nastaví ho jako novou hodnotu `Greetings`. To způsobí, že nové aplikace, Greetings.exe, vytvořit ve složce \Bin\.  
  
2.  Pokud chcete ověřit, že složka \Bin\ obsahuje MSBuildSample aplikace a novou aplikaci pozdrav, zadejte **dir Bin**.  
  
3.  Testování aplikace pozdrav zadáním **Bin\Greetings**.  
  
     **Hello, world!** by se zobrazit zpráva.  
  
4.  Odstranit aplikaci MSBuildSample zadáním **msbuild helloworld.csproj /t: vyčištění**.  
  
     Toto spouští úlohu vyčištění odebrat aplikaci, která má výchozí `AssemblyName` hodnotu vlastnosti `MSBuildSample`.  
  
5.  Odstranit aplikaci pozdrav zadáním **msbuild helloworld.csproj /t: Vyčištění /p:AssemblyName = pozdrav**.  
  
     Toto spouští úlohu vyčištění odebrat aplikaci, která má daném **AssemblyName** hodnotu vlastnosti `Greetings`.  
  
6.  Chcete-li ověřit, že složka \Bin\ je teď prázdný, zadejte **dir Bin**.  
  
7.  Typ **msbuild**.  
  
     I když není zadaný soubor projektu, sestavení nástroje MSBuild helloworld.csproj soubor, protože v aktuální složce je pouze jeden soubor projektu. To způsobí, že aplikace MSBuildSample vytvořit ve složce \Bin\.  
  
     Pokud chcete ověřit, že složka \Bin\ obsahuje MSBuildSample aplikace, zadejte **dir Bin**.  
  
## <a name="building-incrementally"></a>Přírůstkové sestavování  
 Se dá zjistit MSBuild vytvořit cíl pouze v případě, že došlo ke změně zdrojových souborů nebo cíl závisí na cílové soubory. MSBuild používá časové razítko souboru k určení, zda byl změněn.  
  
#### <a name="to-build-incrementally"></a>Chcete-li přírůstkové sestavování  
  
1.  V souboru projektu přidejte tyto atributy otevírání cíl sestavení:  
  
    ```  
    Inputs="@(Compile)" Outputs="$(OutputPath)$(AssemblyName).exe"  
    ```  
  
     Tato hodnota určuje, že cíl sestavení závisí na vstupní soubory, které jsou určené v `Compile` skupiny položek a že je cíl výstupního souboru aplikace.  
  
     Výsledný cíl sestavení by měla vypadat přibližně následující kód:  
  
    ```xml  
    <Target Name="Build" Inputs="@(Compile)" Outputs="$(OutputPath)$(AssemblyName).exe">  
      <MakeDir Directories="$(OutputPath)" Condition="!Exists('$(OutputPath)')" />  
      <Csc Sources="@(Compile)" OutputAssembly="$(OutputPath)$(AssemblyName).exe" />  
    </Target>  
    ```  
  
2.  Testování cíl sestavení zadáním **msbuild /v:d** na příkazovém řádku.  
  
     Mějte na paměti, že helloworld.csproj je výchozí soubor projektu a toto sestavení je výchozí cíl.  
  
     **/V:d** přepínač určuje podrobný popis procesu sestavení.  
  
     Měla by se zobrazit tyto řádky:  
  
     **Cíl "Sestavení" bude vynechán, protože všechny výstupní soubory jsou aktuální s ohledem na vstupní soubory.**  
  
     **Vstupní soubory: HelloWorld.cs**  
  
     **Výstupní soubory: BinMSBuildSample.exe**  
  
     MSBuild přeskočí cíl sestavení, protože žádné zdrojové soubory změnily od posledního byla vytvořena.  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje soubor projektu, který se zkompiluje [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikace a do protokolu zaznamená zprávu, která obsahuje název výstupního souboru.  
  
### <a name="code"></a>Kód  
  
```xml
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <!-- Set the application name as a property -->  
    <PropertyGroup>  
        <appname>HelloWorldCS</appname>  
    </PropertyGroup>  
  
    <!-- Specify the inputs by type and file name -->  
    <ItemGroup>  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">  
        <!-- Run the Visual C# compilation using input files of type CSFile -->  
        <CSC  
            Sources = "@(CSFile)"  
            OutputAssembly = "$(appname).exe">  
            <!-- Set the OutputAssembly attribute of the CSC task  
            to the name of the executable file that is created -->  
            <Output  
                TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
</Project>  
```  
  
### <a name="comments"></a>Komentáře  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje soubor projektu, který se zkompiluje [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] aplikace a do protokolu zaznamená zprávu, která obsahuje název výstupního souboru.  
  
### <a name="code"></a>Kód  
  
```xml  
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <!-- Set the application name as a property -->  
    <PropertyGroup>  
        <appname>HelloWorldVB</appname>  
    </PropertyGroup>  
  
    <!-- Specify the inputs by type and file name -->  
    <ItemGroup>  
        <VBFile Include = "consolehwvb1.vb"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">      
        <!-- Run the Visual Basic compilation using input files of type VBFile -->  
        <VBC  
            Sources = "@(VBFile)"  
            OutputAssembly= "$(appname).exe">  
            <!-- Set the OutputAssembly attribute of the VBC task  
            to the name of the executable file that is created -->  
            <Output  
                TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </VBC>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
</Project>  
```  
  
## <a name="whats-next"></a>Co je další?  
 Visual Studio můžete automaticky provést většinu činností, které se zobrazí v tomto návodu. Další informace o použití sady Visual Studio vytvořit, upravit, vytvářet a testovat soubory projektu nástroje MSBuild, najdete v tématu [návod: použití nástroje MSBuild](../msbuild/walkthrough-using-msbuild.md).  
  
## <a name="see-also"></a>Viz také  
[Přehled nástroje MSBuild](../msbuild/msbuild.md)  
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)