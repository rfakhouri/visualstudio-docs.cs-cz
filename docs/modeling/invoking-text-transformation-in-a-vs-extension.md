---
title: "Volání transformací textu v rozšíření VS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64674976-841f-43cb-8e61-0645c8a89eec
caps.latest.revision: "5"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 40ad4b98b29fe4d54fc3126f49c0454eafc4454d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="invoking-text-transformation-in-a-vs-extension"></a>Volání transformací textu v rozšíření VS
Pokud píšete rozšíření sady Visual Studio, jako je například příkazu nabídky nebo [jazyka domény](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md), je možné použít službu ukázka text k transformaci textové šablony. Získat <xref:Microsoft.VisualStudio.TextTemplating.VSHost.STextTemplating> služby a vysílat <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ITextTemplating>.  
  
## <a name="getting-the-text-templating-service"></a>Získání služby šablonování textu  
  
```csharp  
using Microsoft.VisualStudio.TextTemplating;  
using Microsoft.VisualStudio.TextTemplating.VSHost;  
...  
// Get a service provider - how you do this depends on the context:  
IServiceProvider serviceProvider = ...; // An instance of EnvDTE, for example   
  
// Get the text template service:  
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;  
  
// Process a text template:  
string result = t4.ProcessTemplate(filePath, System.IO.File.ReadAllText(filePath));  
  
```  
  
## <a name="passing-parameters-to-the-template"></a>Předání parametrů do šablony  
 Do šablony můžete předávat parametry. V šabloně, můžete získat hodnoty parametrů pomocí `<#@parameter#>` – direktiva.  
  
 Jako typ parametru je nutné použít typ, který lze serializovat nebo zařadit. To znamená typ musí být deklarována s <xref:System.SerializableAttribute>, nebo musí být odvozen od <xref:System.MarshalByRefObject>. Toto omezení je nezbytné, protože textová šablona se vykonává v samostatné doméně AppDomain. Všechny vestavěné typy jako **System.String** a **System.Int32** jsou serializable.  
  
 Chcete-li předat hodnoty parametrů, volající kód umístěte hodnoty buď v `Session` slovník, nebo v <xref:System.Runtime.Remoting.Messaging.CallContext>.  
  
 Následující příklad používá obě metody k transformaci krátké testovací šablony:  
  
```  
using Microsoft.VisualStudio.TextTemplating;  
using Microsoft.VisualStudio.TextTemplating.VSHost;  
...  
// Get a service provider - how you do this depends on the context:  
IServiceProvider serviceProvider = dte;   
  
// Get the text template service:  
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;  
ITextTemplatingSessionHost sessionHost = t4 as ITextTemplatingSessionHost;  
  
// Create a Session in which to pass parameters:  
sessionHost.Session = sessionHost.CreateSession();  
sessionHost.Session["parameter1"] = "Hello";  
sessionHost.Session["parameter2"] = DateTime.Now;  
  
// Pass another value in CallContext:  
System.Runtime.Remoting.Messaging.CallContext.LogicalSetData("parameter3", 42);  
  
// Process a text template:  
string result = t4.ProcessTemplate("",  
   // This is the test template:  
   "<#@parameter type=\"System.String\" name=\"parameter1\"#>"  
 + "<#@parameter type=\"System.DateTime\" name=\"parameter2\"#>"  
 + "<#@parameter type=\"System.Int32\" name=\"parameter3\"#>"  
 + "Test: <#=parameter1#>    <#=parameter2#>    <#=parameter3#>");  
  
// This test code yields a result similar to the following line:  
//     Test: Hello    07/06/2010 12:37:45    42  
  
```  
  
## <a name="error-reporting-and-the-output-directive"></a>Hlášení chyb a direktiva output  
 Chyby, ke kterým dochází v průběhu zpracování se zobrazí na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno chyb. Kromě toho můžete být upozorněni zadáním zpětné volání, které implementuje chyb <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ITextTemplatingCallback>.  
  
 Pokud chcete zapisovat do souboru výsledný řetězec, můžete chtít vědět, jaké příponu souboru a kódování zadané v `<#@output#>` direktivy v šabloně. Tyto informace budou do zpětného volání rovněž předány. Další informace najdete v tématu [T4 – direktiva Output](../modeling/t4-output-directive.md).  
  
```csharp  
void ProcessMyTemplate(string MyTemplateFile)  
{  
  string templateContent = File.ReadAllText(MyTemplateFile);  
  T4Callback cb = new T4Callback();  
  // Process a text template:  
  string result = t4.ProcessTemplate(MyTemplateFile, templateContent, cb);  
  // If there was an output directive in the MyTemplateFile,  
  // then cb.SetFileExtension() will have been called.  
  // Determine the output file name:  
  string resultFileName =   
    Path.Combine(Path.GetDirectoryName(MyTemplateFile),   
        Path.GetFileNameWithoutExtension(MyTemplateFile))   
      + cb.fileExtension;  
  // Write the processed output to file:  
  File.WriteAllText(resultFileName, result, cb.outputEncoding);  
  // Append any error messages:  
  if (cb.errorMessages.Count > 0)  
  {  
    File.AppendAllLines(resultFileName, cb.errorMessages);  
  }  
}  
  
class T4Callback : ITextTemplatingCallback  
{  
  public List<string> errorMessages = new List<string>();  
  public string fileExtension = ".txt";  
  public Encoding outputEncoding = Encoding.UTF8;  
  
  public void ErrorCallback(bool warning, string message, int line, int column)  
  { errorMessages.Add(message); }  
  
  public void SetFileExtension(string extension)  
  { fileExtension = extension; }  
  
  public void SetOutputEncoding(Encoding encoding, bool fromOutputDirective)  
  { outputEncoding = encoding; }  
}  
  
```  
  
 Kód lze testovat pomocí souboru šablony, který je podobný následujícímu:  
  
```  
<#@output extension=".htm" encoding="ASCII"#>  
<# int unused;  // Compiler warning "unused variable"  
#>  
Sample text.  
```  
  
 Upozornění kompilátoru se objeví v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno chyb ale bude také generovat volání `ErrorCallback`.  
  
## <a name="reference-parameters"></a>Parametry odkazu  
 Můžete předat hodnoty z textové šablony pomocí – třída parametru, který je odvozený od <xref:System.MarshalByRefObject>.  
  
## <a name="related-topics"></a>Související témata  
 Vygenerování textu z předzpracované textové šablony:  
 Volání `TransformText()` metoda generované třídy. Další informace najdete v tématu [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
 Pro vygenerování textu mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření:  
 Definujte vlastního hostitele. Další informace najdete v tématu [zpracování textových šablon pomocí vlastního hostitele](../modeling/processing-text-templates-by-using-a-custom-host.md).  
  
 Vygenerování zdrojového kódu, který lze později zkompilovat a spustit:  
 Volání `t4.PreprocessTemplate()` metodu <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ITextTemplating>.
