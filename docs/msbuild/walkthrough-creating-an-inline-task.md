---
title: 'Návod: Vytvoření vložené úlohy | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, tutorial
- MSBuild, tasks
ms.assetid: 438194cb-668c-41a9-a7e2-c118d14c1ea7
caps.latest.revision: 14
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fb08d3f4774f0d21c44a29414955f30509456757
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-creating-an-inline-task"></a>Návod: Vytvoření vložené úlohy
Úlohy nástroje MSBuild obvykle vytváří kompilování třídu, která implementuje <xref:Microsoft.Build.Framework.ITask> rozhraní. Od verze rozhraní .NET Framework verze 4, můžete vytvořit úlohy vložené v souboru projektu. Chcete-li vytvořit samostatné sestavení pro hostování úlohy nemáte. Další informace najdete v tématu [vložené úlohy](../msbuild/msbuild-inline-tasks.md).  
  
 Tento návod ukazuje, jak vytvořit a spustit tyto vložené úlohy:  
  
-   Úloha, která nemá žádné vstupní nebo výstupní parametry.  
  
-   Úloha, která má jeden vstupní parametr a žádná výstupní parametry.  
  
-   Úloha, která má dva vstupní parametry a jednu výstupní parametr, který vrací ve vlastnosti nástroje MSBuild.  
  
-   Úloha, která má dva vstupní parametry a jednu výstupní parametr, který vrátí položky nástroje MSBuild.  
  
 Vytvoření a spuštění úlohy, použijte sadu Visual Studio a **okno příkazového řádku Visual Studio**, a to takto:  
  
-   Vytvořte soubor projektu nástroje MSBuild pomocí sady Visual Studio.  
  
-   Upravte soubor projektu v sadě Visual Studio k vytvoření vložené úlohy.  
  
-   Použití **okno příkazového řádku** se projekt sestavil a podívejte se na výsledky.  
  
## <a name="creating-and-modifying-an-msbuild-project"></a>Vytvoření a úprava projektu nástroje MSBuild  
 Systém projektu sady Visual Studio je založen na MSBuild. Proto můžete vytvořit soubor sestavení projektu pomocí sady Visual Studio. V této části vytvoříte soubor projektu Visual C#. (Místo toho můžete můžete vytvořit soubor projektu jazyka Visual Basic. V kontextu tohoto kurzu rozdíl mezi dvěma projektu soubory je menší.)  
  
#### <a name="to-create-and-modify-a-project-file"></a>Vytvoření a změna souboru projektu  
  
1.  V sadě Visual Studio na **soubor** nabídky, klikněte na tlačítko **nový** a pak klikněte na **projektu**.  
  
2.  V **nový projekt** dialogové okno, vyberte Visual C# typ projektu a pak vyberte **formulářové aplikace Windows** šablony. V **název** zadejte `InlineTasks`. Zadejte **umístění** pro řešení, například `D:\`. Ujistěte se, že **vytvořit adresář pro řešení** je vybraná, **přidat do správy zdrojového kódu** není zaškrtnuto, a **název řešení** je `InlineTasks`.  
  
     Klikněte na tlačítko **OK** k vytvoření souboru projektu.  
  
3.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu InlineTasks a pak klikněte na tlačítko **uvolnit projekt**.  
  
4.  Znovu klikněte pravým tlačítkem na uzel projektu a pak klikněte na **upravit InlineTasks.csproj**.  
  
     Soubor projektu se zobrazí v editoru kódu.  
  
## <a name="adding-a-basic-hello-task"></a>Přidání úlohu základní Hello  
 Nyní, přidejte do souboru projektu základní úlohu, která zobrazí zprávu "Hello, world!" Také přidáte cíl výchozí TestBuild k vyvolání úlohy.  
  
#### <a name="to-add-a-basic-hello-task"></a>Chcete-li přidat úloha základní hello  
  
1.  V kořenovém `Project` uzlu, změny `DefaultTargets` atribut `TestBuild`. Výsledná `Project` uzlu by měl vypadat podobně jako tento příklad:  
  
     `<Project ToolsVersion="4.0" DefaultTargets="TestBuild" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">`  
  
2.  Přidejte následující vložené úlohy a cílový soubor projektu těsně před `</Project>` značky.  
  
    ```xml  
    <UsingTask TaskName="Hello" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v4.0.dll" >  
      <ParameterGroup />  
      <Task>  
        <Code Type="Fragment" Language="cs">  
          Log.LogMessage("Hello, world!", MessageImportance.High);  
        </Code>  
      </Task>  
    </UsingTask>  
    <Target Name="TestBuild">  
      <Hello />  
    </Target>  
    ```  
  
3.  Uložte soubor projektu.  
  
 Tento kód vytvoří vložené úlohy s názvem Hello a nemá žádné parametry, odkazy, nebo `Using` příkazy. Úloha Hello obsahuje pouze jeden řádek kódu, který zobrazí zprávu hello v zařízení výchozí protokolování, obvykle v okně konzoly.  
  
### <a name="running-the-hello-task"></a>Spuštění úlohy Hello  
 Spuštění nástroje MSBuild pomocí **okno příkazového řádku** vytvořit úlohu Hello a zpracování TestBuild cíl, který vyvolá ho.  
  
##### <a name="to-run-the-hello-task"></a>Ke spuštění této úlohy Hello  
  
1.  Klikněte na tlačítko **spustit**, klikněte na tlačítko **všechny programy**a vyhledejte **nástroje sady Visual Studio** složky a klikněte na tlačítko **Visual Studio – příkazový řádek**.  
  
2.  V **okno příkazového řádku**, vyhledejte složku, která obsahuje soubor projektu, v takovém případě D:\InlineTasks\InlineTasks\\.  
  
3.  Typ **msbuild** bez příkaz přepínače a potom stiskněte klávesu ENTER. Ve výchozím nastavení vytvoří soubor InlineTasks.csproj a zpracuje výchozí cíl TestBuild, které vyvolá úloha Hello.  
  
4.  Zkontrolujte výstup v **okno příkazového řádku**. Měli byste vidět tento řádek:  
  
     `Hello, world!`  
  
    > [!NOTE]
    >  Pokud nevidíte uvítací zprávu, zkuste znovu uložit soubor projektu a spusťte úlohu Hello.  
  
 Podle střídavých mezi editoru kódu a **okno příkazového řádku**, můžete změnit soubor projektu a rychle zobrazit výsledky.  
  
## <a name="defining-the-echo-task"></a>Definování úloh Echo  
 Vytvoření vložené úlohy, která přijímá řetězcový parametr a zobrazí řetězec na výchozí protokolování zařízení.  
  
#### <a name="to-define-the-echo-task"></a>Chcete-li definovat úlohu Echo  
  
1.  V editoru kódu nahraďte Hello úloh a TestBuild cíle pomocí následující kód.  
  
    ```xml  
    <UsingTask TaskName="Echo" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v4.0.dll" >  
      <ParameterGroup>  
        <Text Required="true" />  
      </ParameterGroup>  
      <Task>  
        <Code Type="Fragment" Language="cs">  
          Log.LogMessage(Text, MessageImportance.High);  
        </Code>  
      </Task>  
    </UsingTask>  
    <Target Name="TestBuild">  
      <Echo Text="Greetings!" />  
    </Target>  
    ```  
  
2.  V **okno příkazového řádku**, typ **msbuild** bez příkaz přepínače a potom stiskněte klávesu ENTER. Ve výchozím nastavení to procesů výchozí cíl TestBuild, které vyvolá úloha odezvu.  
  
3.  Zkontrolujte výstup v **okno příkazového řádku**. Měli byste vidět tento řádek:  
  
     `Greetings!`  
  
 Tento kód definuje vložené úlohy s názvem Echo a má jenom jeden povinný vstupní parametr Text. Ve výchozím nastavení jsou parametry typu System.String. Hodnota parametru Text nastavena, když cíl TestBuild vyvolá úloha odezvu.  
  
## <a name="defining-the-adder-task"></a>Definování úloh přidávání  
 Vytvoření vložené úlohy, která přidá dva parametry celé číslo a vysílá jejich součet jako ve vlastnosti nástroje MSBuild.  
  
#### <a name="to-define-the-adder-task"></a>Chcete-li definovat přidávání úloh  
  
1.  V editoru kódu nahraďte Echo úloh a TestBuild cíle pomocí následující kód.  
  
    ```xml  
    <UsingTask TaskName="Adder" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v4.0.dll" >  
      <ParameterGroup>  
        <A ParameterType="System.Int32" Required="true" />  
        <B ParameterType="System.Int32" Required="true" />  
        <C ParameterType="System.Int32" Output="true" />  
      </ParameterGroup>  
      <Task>  
        <Code Type="Fragment" Language="cs">  
          C = A + B;  
        </Code>  
      </Task>  
    </UsingTask>    
    <Target Name="TestBuild">  
      <Adder A="4" B="5">  
        <Output PropertyName="Sum" TaskParameter="C" />  
      </Adder>  
      <Message Text="The sum is $(Sum)" Importance="High" />  
    </Target>  
    ```  
  
2.  V **okno příkazového řádku**, typ **msbuild** bez příkaz přepínače a potom stiskněte klávesu ENTER. Ve výchozím nastavení to procesů výchozí cíl TestBuild, které vyvolá úloha odezvu.  
  
3.  Zkontrolujte výstup v **okno příkazového řádku**. Měli byste vidět tento řádek:  
  
     `The sum is 9`  
  
 Tento kód definuje vložené úlohy, který je pojmenován přidávání a má dva požadované vstupní parametry celé číslo, A a B, a jeden celočíselný výstupní parametr, C. Přidávání úkolů přidá dva vstupní parametry a vrátí součet ve výstupní parametr. Součet je vygenerované jako vlastnosti MSBuild `Sum`. Hodnoty vstupní parametry jsou nastaveny při cíl TestBuild vyvolá přidávání úkolů.  
  
## <a name="defining-the-regx-task"></a>Definování úloh RegX  
 Vytvoření vložené úlohy, který přijímá skupinu položek a regulární výraz a vrátí seznam všech položek, které mají obsah souboru, který se shoduje s výrazem.  
  
#### <a name="to-define-the-regx-task"></a>Chcete-li definovat úlohu RegX  
  
1.  V editoru kódu místo přidávání úkolů a TestBuild cíle pomocí následující kód.  
  
    ```xml  
    <UsingTask TaskName="RegX" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v4.0.dll" >  
      <ParameterGroup>  
        <Expression Required="true" />  
        <Files ParameterType="Microsoft.Build.Framework.ITaskItem[]" Required="true" />  
        <Result ParameterType="Microsoft.Build.Framework.ITaskItem[]" Output="true" />  
      </ParameterGroup>  
      <Task>  
        <Using Namespace="System.Text.RegularExpressions"/>  
        <Code Type="Fragment" Language="cs">  
    <![CDATA[  
          if (Files.Length > 0)  
          {  
            Result = new TaskItem[Files.Length];  
            for (int i = 0; i < Files.Length; i++)  
            {  
              ITaskItem item = Files[i];  
              string path = item.GetMetadata("FullPath");  
              using(StreamReader rdr = File.OpenText(path))  
              {  
                if (Regex.Match(rdr.ReadToEnd(), Expression).Success)  
                {  
                  Result[i] = new TaskItem(item.ItemSpec);  
                }  
              }  
            }  
          }  
    ]]>  
        </Code>  
      </Task>  
    </UsingTask>    
    <Target Name="TestBuild">  
      <RegX Expression="public|protected" Files="@(Compile)">  
        <Output ItemName="MatchedFiles" TaskParameter="Result" />  
      </RegX>  
      <Message Text="Input files: @(Compile)" Importance="High" />  
      <Message Text="Matched files: @(MatchedFiles)" Importance="High" />  
    </Target>  
    ```  
  
2.  V **okno příkazového řádku**, typ **msbuild** bez příkaz přepínače a potom stiskněte klávesu ENTER. Ve výchozím nastavení to procesů výchozí cíl TestBuild, které vyvolá RegX úloh.  
  
3.  Zkontrolujte výstup v **okno příkazového řádku**. Měli byste vidět tyto řádky:  
  
     `Input files: Form1.cs;Form1.Designer.cs;Program.cs;Properties\AssemblyInfo.cs;Properties\Resources.Designer.cs;Properties\Settings.Designer.cs`  
  
     `Matched files: Form1.cs;Form1.Designer.cs;Properties\Settings.Designer.cs`  
  
 Tento kód definuje vložené úlohy, který má název RegX a tyto tři parametry:  
  
-   `Expression` je vstupní parametr požadované řetězec, který má hodnotu, která je regulární výraz odpovídat. V tomto příkladu odpovídá výraz slova "veřejná" nebo "chráněné".  
  
-   `Files` je vstupní parametr požadovaná položka seznamu, který má hodnotu, která je seznam souborů, které má být vyhledán shody. V tomto příkladu `Files` je nastaven na `Compile` položky, které zobrazí zdrojové soubory projektu.  
  
-   `Result` je výstupní parametr, který má hodnotu, která je seznam souborů, které mají obsah, které odpovídají regulárnímu výrazu.  
  
 Když cíl TestBuild vyvolá úloha RegX jsou nastavena hodnota vstupní parametry. Úloha RegX přečte každý soubor a vrátí seznam souborů, které odpovídají regulárnímu výrazu. Tento seznam se vrátí jako `Result` výstupní parametr, který je vygenerované jako položky nástroje MSBuild `MatchedFiles`.  
  
### <a name="handling-reserved-characters"></a>Zpracování vyhrazené znaky  
 Analyzátor MSBuild zpracovává vložené úlohy ve formátu XML. Znaky, které obsahují rezervované význam v XML, například "\<" a ">", jsou zjištěna a zpracovávají, jako kdyby byly XML a ne zdrojový kód rozhraní .NET. K obsahují vyhrazené znaky v kódu výrazy, například `Files.Length > 0`, zapisovat `Code` element tak, aby její obsah se obsažených ve výrazu CDATA následujícím způsobem:  
  
 `<Code Type="Fragment" Language="cs">`  
  
 `<![CDATA[`  
  
 `// Your code goes here.`  
  
 `]]>`  
  
 `</Code>`  
  
## <a name="see-also"></a>Viz také  
 [Vložené úlohy](../msbuild/msbuild-inline-tasks.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Cíle](../msbuild/msbuild-targets.md)