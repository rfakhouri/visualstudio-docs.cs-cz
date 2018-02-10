---
title: "Návod: Připojování hostitele k generovaného procesoru direktiv | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- walkthroughs [text templates], connecting host to processor
- text templates, custom directive hosts
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: b506957c80b1e678bab75afedb8a50621d611220
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="walkthrough-connecting-a-host-to-a-generated-directive-processor"></a>Návod: Připojení hostitele k procesoru vygenerovaných direktiv
Můžete napsat vlastního hostitele, který zpracovává textové šablony. Základní vlastní hostitel je znázorněn v [návod: vytvoření vlastního hostitele textových šablon](../modeling/walkthrough-creating-a-custom-text-template-host.md). Můžete rozšířit tohoto hostitele přidat funkce, jako je vytváření více výstupních souborů.  
  
 V tomto návodu rozbalte vlastního hostitele tak, aby podporoval textové šablony, které volají procesory direktiv. Když definujete jazyk specifické pro doménu, generuje *procesoru direktiv* modelu domény. Procesoru direktiv usnadňuje uživatelům zapisovat šablony, které přístup k modelu, přičemž redukuje nutnost zápisu sestavení a importovat direktivy v šablonách.  
  
> [!WARNING]
>  Tento názorný postup je založený na [návod: vytvoření vlastního hostitele textových šablony](../modeling/walkthrough-creating-a-custom-text-template-host.md). Tento postup proveďte jako první.  
  
 Tento návod zahrnuje následující úlohy:  
  
-   Pomocí [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] ke generování procesoru direktiv, která je založená na modelu domény.  
  
-   Připojování vlastního hostitele textových šablon generovaného direktivy procesor.  
  
-   Testování vlastního hostitele s generovaného procesoru direktiv.  
  
## <a name="prerequisites"></a>Požadavky  
 Pokud chcete definovat DSL, je třeba nainstalovat následující součásti:  
  
|||  
|-|-|  
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|  
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|  
|Visual Studio vizualizace a modelování SDK||  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
  
 Kromě toho musí mít vlastní text transformace šablony vytvořené v [návod: vytvoření vlastního hostitele textových šablon](../modeling/walkthrough-creating-a-custom-text-template-host.md).  
  
## <a name="using-domain-specific-language-tools-to-generate-a-directive-processor"></a>Pomocí nástroje jazyka domény ke generování procesoru direktiv  
 V tomto návodu použijte Průvodce specifické pro doménu jazyk Designer pro vytvoření domény jazyka pro řešení DSLMinimalTest.  
  
#### <a name="to-use-domain-specific-language-tools-to-generate-a-directive-processor-that-is-based-on-a-domain-model"></a>Jazykové nástroje specifické pro doménu používat ke generování procesoru direktiv, která je založená na modelu domény  
  
1.  Vytvořte řešení jazyka domény, který má následující vlastnosti:  
  
    -   Název: DSLMinimalTest  
  
    -   Šablona řešení: minimální jazyk  
  
    -   Příponu souboru: min.  
  
    -   Název společnosti: Fabrikam  
  
     Další informace o vytváření řešení jazyka domény najdete v tématu [postupy: vytvoření řešení jazyk specifické pro doménu](../modeling/how-to-create-a-domain-specific-language-solution.md).  
  
2.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
    > [!IMPORTANT]
    >  Tento krok generuje procesoru direktiv a přidá klíč pro něj v registru.  
  
3.  Na **ladění** nabídky, klikněte na tlačítko **spustit ladění**.  
  
     Druhou instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otevře.  
  
4.  V experimentální sestavení v **Průzkumníku řešení**, poklikejte na soubor **sample.min**.  
  
     Soubor se otevře v návrháři. Všimněte si, že model má dva elementy, ExampleElement1 a ExampleElement2 a propojení mezi nimi.  
  
5.  Zavřete druhou instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
6.  Uložte řešení a pak zavřete Editor jazyk specifické pro doménu.  
  
## <a name="connecting-a-custom-text-template-host-to-a-directive-processor"></a>Připojování vlastního hostitele textových šablon do procesoru direktiv  
 Po vygenerování procesoru direktiv připojíte procesoru direktiv a hostitele šablon vlastní text, který jste vytvořili v [návod: vytvoření vlastního hostitele textových šablon](../modeling/walkthrough-creating-a-custom-text-template-host.md).  
  
#### <a name="to-connect-a-custom-text-template-host-to-the-generated-directive-processor"></a>Pro připojení vlastního hostitele textových šablon pro generovaný procesoru direktiv  
  
1.  Otevřete CustomHost řešení.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat odkaz na**.  
  
     **Přidat odkaz na** otevře se dialogové okno s **.NET** kartě Zobrazit.  
  
3.  Přidejte následující odkazy:  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.11.0  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0  
  
    -   Microsoft.VisualStudio.TextTemplating.11.0  
  
    -   Microsoft.VisualStudio.TextTemplating.Interfaces.11.0  
  
    -   Microsoft.VisualStudio.TextTemplating.Modeling.11.0  
  
    -   Microsoft.VisualStudio.TextTemplating.VSHost.11.0  
  
4.  V horní části souboru Program.cs nebo Module1.vb přidejte následující řádek kódu:  
  
    ```csharp  
    using Microsoft.Win32;  
    ```  
  
    ```vb  
    Imports Microsoft.Win32  
    ```  
  
5.  Vyhledejte kód pro vlastnost `StandardAssemblyReferences`a nahraďte ji následujícím kódem:  
  
    > [!NOTE]
    >  V tomto kroku přidáte odkazy na sestavení, které jsou vyžadované generovaného procesoru direktiv, která bude podporovat váš hostitel.  
  
    ```csharp  
    //the host can provide standard assembly references  
    //the engine will use these references when compiling and  
    //executing the generated transformation class  
    //--------------------------------------------------------------  
    public IList<string> StandardAssemblyReferences  
    {  
        get  
        {  
            return new string[]  
            {  
                //if this host searches standard paths and the GAC  
                //we can specify the assembly name like this:  
                //"System"  
                //since this host only resolves assemblies from the   
                //fully qualified path and name of the assembly  
                //this is a quick way to get the code to give us the  
                //fully qualified path and name of the System assembly  
                //---------------------------------------------------------  
                typeof(System.Uri).Assembly.Location,  
                            typeof(System.Uri).Assembly.Location,  
                typeof(Microsoft.VisualStudio.Modeling.ModelElement).Assembly.Location,  
                typeof(Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape).Assembly.Location,  
                typeof(Microsoft.VisualStudio.TextTemplating.VSHost.ITextTemplating).Assembly.Location,  
                typeof(Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation).Assembly.Location  
  
            };  
        }  
    }  
    ```  
  
6.  Vyhledejte kód pro funkci `ResolveDirectiveProcessor`a nahraďte ji následujícím kódem:  
  
    > [!IMPORTANT]
    >  Tento kód obsahuje pevně zakódovaný odkazy na název generovaného procesoru direktiv, ke kterému se chcete připojit. Bylo možné snadno provádět to další obecné, v takovém případě hledá všechny procesory direktiv uvedený v registru a pokusí se najít shodu. V takovém případě by hostiteli spolupracovat s všechny vygenerované procesoru direktiv.  
  
    ```csharp  
    //the engine calls this method based on the directives the user has   
            //specified it in the text template  
            //this method can be called 0, 1, or more times  
            //---------------------------------------------------------------------  
            public Type ResolveDirectiveProcessor(string processorName)  
            {  
                //check the processor name, and if it is the name of the processor the   
                //host wants to support, return the type of the processor  
                //---------------------------------------------------------------------  
                if (string.Compare(processorName, "DSLMinimalTestDirectiveProcessor", StringComparison.InvariantCultureIgnoreCase) == 0)  
                {  
                    try  
                    {  
                        string keyName = @"Software\Microsoft\VisualStudio\10.0Exp_Config\TextTemplating\DirectiveProcessors\DSLMinimalTestDirectiveProcessor";  
                        using (RegistryKey specificKey = Registry.CurrentUser.OpenSubKey(keyName))  
                        {  
                            if (specificKey != null)  
                            {  
                                List<string> names = new List<String>(specificKey.GetValueNames());  
                                string classValue = specificKey.GetValue("Class") as string;  
                                if (!string.IsNullOrEmpty(classValue))  
                                {  
                                    string loadValue = string.Empty;  
                                    System.Reflection.Assembly processorAssembly = null;  
                                    if (names.Contains("Assembly"))  
                                    {  
                                        loadValue = specificKey.GetValue("Assembly") as string;  
                                        if (!string.IsNullOrEmpty(loadValue))  
                                        {  
                                            //the assembly must be installed in the GAC  
                                            processorAssembly = System.Reflection.Assembly.Load(loadValue);  
                                        }  
                                    }  
                                    else if (names.Contains("CodeBase"))  
                                    {  
                                        loadValue = specificKey.GetValue("CodeBase") as string;  
                                        if (!string.IsNullOrEmpty(loadValue))  
                                        {  
                                            //loading local assembly  
                                            processorAssembly = System.Reflection.Assembly.LoadFrom(loadValue);  
                                        }  
                                    }  
                                    if (processorAssembly == null)  
                                    {  
                                        throw new Exception("Directive Processor not found");  
                                    }  
                                    Type processorType = processorAssembly.GetType(classValue);  
                                    if (processorType == null)  
                                    {  
                                        throw new Exception("Directive Processor not found");  
                                    }  
                                    return processorType;  
                                }  
                            }  
                        }  
                    }  
                    catch (Exception e)  
                    {  
                        //if the directive processor can not be found, throw an error  
                        throw new Exception("Directive Processor not found");  
                    }  
                }  
  
                //if the directive processor is not one this host wants to support  
                throw new Exception("Directive Processor not supported");  
            }  
    ```  
  
7.  Na **soubor** nabídky, klikněte na tlačítko **Uložit vše**.  
  
8.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
## <a name="testing-the-custom-host-with-the-directive-processor"></a>Testování vlastního hostitele s procesoru direktiv  
 K testování vlastního hostitele textových šablon, musíte nejprve napsat textové šablony, který volá generovaného procesoru direktiv. Potom můžete spustit vlastního hostitele, jí předat název textové šablony a ověřte, že je správně zpracovat direktivu.  
  
#### <a name="to-create-a-text-template-to-test-the-custom-host"></a>Vytvoření textové šablony pro testování vlastního hostitele  
  
1.  Vytvořte textový soubor s názvem `TestTemplateWithDP.tt`. Textový editor, například Poznámkový blok, můžete použít k vytvoření souboru.  
  
2.  Do tohoto textového souboru přidejte následující text:  
  
    > [!NOTE]
    >  Programovací jazyk textové šablony nemusí odpovídat vlastního hostitele.  
  
    ```csharp  
    Text Template Host Test  
  
    <#@ template debug="true" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>  
    <# //this is the call to the examplemodel directive in the generated directive processor #>  
    <#@ DSLMinimalTest processor="DSLMinimalTestDirectiveProcessor" requires="fileName='<Your Path>\Sample.min'" provides="ExampleModel=ExampleModel" #>  
    <# //uncomment this line to test that the host allows the engine to set the extension #>  
    <# //@ output extension=".htm" #>  
  
    <# //uncomment this line if you want to see the generated transformation class #>  
    <# //System.Diagnostics.Debugger.Break(); #>  
    <# //this code uses the results of the examplemodel directive #>  
    <#  
        foreach ( ExampleElement box in this.ExampleModel.Elements )   
        {   
            WriteLine("Box: {0}", box.Name);  
  
            foreach (ExampleElement linkedTo in box.Targets)  
            {  
                WriteLine("Linked to: {0}", linkedTo.Name);  
            }  
  
            foreach (ExampleElement linkedFrom in box.Sources)  
            {  
                WriteLine("Linked from: {0}", linkedFrom.Name);  
            }  
  
            WriteLine("");  
        }   
    #>  
    ```  
  
    ```vb  
    Text Template Host Test  
  
    <#@ template debug="true" language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>  
  
    <# 'this is the call to the examplemodel directive in the generated directive processor #>  
    <#@ DSLMinimalTest processor="DSLMinimalTestDirectiveProcessor" requires="fileName='<Your Path>\Sample.min'" provides="ExampleModel=ExampleModel" #>  
  
    <# 'Uncomment this line to test that the host allows the engine to set the extension. #>  
    <# '@ output extension=".htm" #>  
  
    <# 'Uncomment this line if you want to see the generated transformation class. #>  
    <# 'System.Diagnostics.Debugger.Break() #>  
  
    <# 'this code uses the results of the examplemodel directive #>  
  
    <#      
       For Each box as ExampleElement In Me.ExampleModel.Elements   
  
           WriteLine("Box: {0}", box.Name)  
  
            For Each LinkedTo as ExampleElement In box.Targets  
                WriteLine("Linked to: {0}", LinkedTo.Name)  
            Next  
  
            For Each LinkedFrom as ExampleElement In box.Sources  
                WriteLine("Linked from: {0}", LinkedFrom.Name)  
            Next  
  
            WriteLine("")  
  
       Next   
    #>  
    ```  
  
3.  V kódu, nahraďte \<vaše cesta > s cestu k souboru Sample.min z návrhu jazyka jste vytvořili v prvním postupu.  
  
4.  Soubor uložte a zavřete.  
  
#### <a name="to-test-the-custom-host"></a>Testování vlastního hostitele  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Zadejte cestu ke spustitelnému souboru vlastního hostitele, ale zatím nemačkejte klávesu ENTER.  
  
     Zadejte například:  
  
     `<YOUR PATH>CustomHost\bin\Debug\CustomHost.exe`  
  
    > [!NOTE]
    >  Místo zadáte adresu, můžete vyhledat soubor CustomHost.exe v **Průzkumníka Windows**a pak přetáhněte soubor do okna příkazového řádku.  
  
3.  Zadejte mezeru.  
  
4.  Zadejte cestu k souboru textové šablony a stiskněte klávesu ENTER.  
  
     Zadejte například:  
  
     `<YOUR PATH>TestTemplateWithDP.txt`  
  
    > [!NOTE]
    >  Místo zadáte adresu, můžete vyhledat soubor TestTemplateWithDP.txt v **Průzkumníka Windows**a pak přetáhněte soubor do okna příkazového řádku.  
  
     Vlastní hostitel aplikace spuštěna a spouští proces transformace textových šablon.  
  
5.  V **Průzkumníka Windows**, přejděte do složky, která obsahuje soubor TestTemplateWithDP.txt.  
  
     Složka také obsahuje soubor TestTemplateWithDP1.txt.  
  
6.  Otevřete tento soubor a podívejte se na výsledky transformace textové šablony.  
  
     Výsledky výstup generovaný text se zobrazí a by měla vypadat takto:  
  
    ```  
    Text Template Host Test  
  
    Box: ExampleElement1  
    Linked to: ExampleElement2  
  
    Box: ExampleElement2  
    Linked from: ExampleElement1  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření vlastního hostitele textových šablon](../modeling/walkthrough-creating-a-custom-text-template-host.md)
