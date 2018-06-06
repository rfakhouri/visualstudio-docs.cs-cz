---
title: 'Návod: Použití rozhraní API profileru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
ms.assetid: c2ae0b3e-a0ca-4967-b4df-e319008f520e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 50b77a343f8fe918fa079a3b4f148407701276c8
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572975"
---
# <a name="walkthrough-using-profiler-apis"></a>Návod: použití rozhraní API profileru
Průvodce používá aplikace v jazyce C# k ukazují, jak používat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace rozhraní API nástroje. Chcete-li omezit množství dat, které jsou shromážděny během profilace instrumentace použijete rozhraní API profileru.  
  
 Kroky v tomto návodu se obecně používají na aplikace C/C++. Pro každý jazyk budete muset nakonfigurovat prostředí sestavení správně.  
  
 Obvykle se spustí při analýze výkonu aplikací pomocí profilace ukázka. Pokud ukázka profilace neposkytuje informace, které zjišťuje problémové místo, profilace instrumentace nabízejí vyšší úroveň podrobností. Profilace instrumentace je velmi užitečná pro zkoumání interakce přístup z více vláken.  
  
 Vyšší úroveň podrobností však znamená, že další data jsou shromažďována. Je možné, že profilace instrumentace vytvoří velké datové soubory. Navíc instrumentace je pravděpodobnější mít dopad na výkon aplikace. Další informace najdete v tématu [pochopit hodnotám dat instrumentace](../profiling/understanding-instrumentation-data-values.md) a [pochopit hodnotám dat vzorkování](../profiling/understanding-sampling-data-values.md)  
  
 Visual Studio profiler umožňuje omezit shromažďování dat. Tento názorný postup nabízí příklad omezení shromažďování dat pomocí rozhraní API profileru. Visual Studio profiler poskytuje rozhraní API pro řízení shromažďování dat z některé aplikace.  
  
 Pro nativní kód sadě Visual Studio profiler rozhraní API jsou v *VSPerf.dll*. Soubor hlaviček, *VSPerf.h*a knihovny importu *VSPerf.lib*, jsou umístěné v *nástrojů nástroje sady Microsoft Visual Studio 9\Team* adresáře.  
  
 Pro spravovaný kód profileru rozhraní API jsou v *Microsoft.VisualStudio.Profiler.dll*. Tuto knihovnu DLL se nachází v *nástrojů nástroje sady Microsoft Visual Studio 9\Team* adresáře. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.Profiler>.  
  
## <a name="prerequisites"></a>Požadavky  
 Tento návod předpokládá, že vaši volbu vývojového prostředí je nakonfigurován pro podporu ladění a vzorkování. Základní informace o těchto nezbytných podmínkách naleznete v následujících tématech:  
  
 [Postupy: Výběr metod shromažďování](../profiling/how-to-choose-collection-methods.md)  
  
 [Postupy: Odkazování na informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)  
  
 Ve výchozím nastavení když se spustí profileru profileru shromažďuje data na globální úrovni. Následující kód na začátku programu změní globální profilace vypnout.  
  
```csharp  
DataCollection.StopProfile(  
ProfileLevel.Global,  
DataCollection.CurrentId);  
```  
  
 Shromažďování dat na příkazovém řádku můžete vypnout bez použití volání rozhraní API. Následující postup předpokládá, prostředí sestavení příkazového řádku je nakonfigurovaná pro spuštění nástrojů pro profilaci a jako vývojové nástroje. To zahrnuje nastavení požadovaná pro vsinstr – a VSPerfCmd. V tématu profilování nástroje příkazového řádku.  
  
## <a name="limit-data-collection-using-profiler-apis"></a>Omezení shromažďování dat pomocí rozhraní API profileru  
  
#### <a name="to-create-the-code-to-profile"></a>Chcete-li vytvořit kód do profilu  
  
1.  Vytvořte nový projekt C# v sadě Visual Studio, nebo použití sestavení příkazového řádku, v závislosti na vaši volbu.  
  
    > [!NOTE]
    >  Buildu musí odkazovat *Microsoft.VisualStudio.Profiler.dll* knihovny, umístěný ve*nástrojů nástroje sady Microsoft Visual Studio 9\Team* adresáře.  
  
2.  Zkopírujte a vložte následující kód do projektu:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using Microsoft.VisualStudio.Profiler;  
  
    namespace ConsoleApplication2  
    {  
        class Program  
        {  
            public class A  
            {  
             private int _x;  
  
             public A(int x)  
             {  
              _x = x;  
             }  
  
             public int DoNotProfileThis()  
             {  
              return _x * _x;  
             }  
  
             public int OnlyProfileThis()  
             {  
              return _x + _x;  
             }  
  
             public static void Main()  
             {  
            DataCollection.StopProfile(  
            ProfileLevel.Global,  
            DataCollection.CurrentId);  
              A a;  
              a = new A(2);  
              int x;      
              Console.WriteLine("2 square is {0}", a.DoNotProfileThis());  
              DataCollection.StartProfile(  
                  ProfileLevel.Global,  
                  DataCollection.CurrentId);  
              x = a.OnlyProfileThis();  
              DataCollection.StopProfile(  
                  ProfileLevel.Global,   
                  DataCollection.CurrentId);  
              Console.WriteLine("2 doubled is {0}", x);  
             }  
            }  
  
        }  
    }  
    ```  
  
#### <a name="to-collect-and-view-data-in-the-visual-studio-ide"></a>Můžete shromažďovat a zobrazovat data v prostředí Visual Studio IDE  
  
1.  Otevřete [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Na **analyzovat** nabídky, přejděte na příkaz **profileru**a potom vyberte **novou relaci výkonu**.  
  
2.  Přidání vaší kompilované binárního souboru ke **cíle** v seznamu **prohlížeč výkonu** okno. Klikněte pravým tlačítkem na **cíle**a potom vyberte **přidat cíl binární**. Najít binární v **přidat cíl binární** dialogové okno a pak klikněte na tlačítko **otevřete**.  
  
3.  Vyberte **instrumentace** z **metoda** na seznamu **prohlížeč výkonu** panelu nástrojů.  
  
4.  Klikněte na tlačítko **spouštění profilace**.  
  
     Profileru instrumentace a provést binárního souboru a vytvoření souboru sestavy výkonu. Soubor sestavy výkonu se zobrazí v **sestavy** uzlu **prohlížeč výkonu**.  
  
5.  Otevřete soubor sestavy výsledný výkon.  
  
 Ve výchozím nastavení když se spustí profileru, bude profileru shromažďovat data na globální úrovni. Následující kód na začátku programu změní globální profilace vypnout.  
  
```csharp  
DataCollection.StopProfile(  
ProfileLevel.Global,  
DataCollection.CurrentId);  
```  
  
#### <a name="to-collect-and-view-data-at-the-command-line"></a>Můžete shromažďovat a zobrazovat data na příkazovém řádku  
  
1.  Zkompilujte ladicí verze, kterou jste vytvořili v postupu "Vytváření kódu do profilu" dříve v tomto návodu ukázkový kód.  
  
2.  Profilu spravované aplikace, zadejte následující příkaz pro nastavení příslušné proměnné prostředí:  
  
     **VsPefCLREnv /traceon**  
  
3.  Zadejte následující příkaz:**vsinstr – \<filename > .exe**  
  
4.  Zadejte následující příkaz:**VSPerfCmd /start:trace output:\<filename > .vsp**  
  
5.  Zadejte následující příkaz:**VSPerfCmd /globaloff**  
  
6.  Spusťte program.  
  
7.  Zadejte následující příkaz:  **/VSPerfCmd Shutdown**  
  
8.  Zadejte následující příkaz:**vsperfreport – /calltrace:\<filename > .vsp**  
  
     A. *csv* soubor je vytvořen v aktuálním adresáři s Výsledná data výkonu.  
  
## <a name="see-also"></a>Viz také:  
 <xref:Microsoft.VisualStudio.Profiler>   
 [Visual Studio profiler referenční dokumentace rozhraní API (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)   
 [Začínáme](../profiling/getting-started-with-performance-tools.md)   
 [Profil z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)