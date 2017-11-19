---
title: "Správa odkazů v projektu | Microsoft Docs"
ms.custom: 
ms.date: 10/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.ProjectPropertiesReferencePaths
- cs.ProjectPropertiesReferencePaths
helpviewer_keywords:
- Visual C# projects, references
- referencing objects, project references
- external component references
- referencing namespaces
- Visual Basic projects, references
- referencing components, external components
- Web references, types of project references
- namespaces [Visual Studio], referencing
- COM components, referencing
- objects [Visual Studio], referencing
ms.assetid: 05d1c51b-44f3-4973-8a11-6c919b08ad62
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4145dda187e726096e2137d2a5fdc0455b6131e2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="managing-references-in-a-project"></a>Správa odkazů v projektu
Než psát kód pro místní externí komponenta nebo připojené služby, projektu musí nejprve obsahovat odkaz na jeho. Odkaz je v podstatě položku v souboru projektu, který obsahuje informace, že Visual Studio se musí vyhledat daná komponenta nebo služba.  

 Chcete-li přidat odkaz, klikněte pravým tlačítkem na uzel odkazy v Průzkumníku řešení a zvolte **přidat odkaz na**. Další informace najdete v tématu [postupy: Přidání nebo odebrání odkazů pomocí Správce odkazů](../ide/how-to-add-or-remove-references-by-using-the-reference-manager.md).  

 ![Přidat odkaz ve Visual C & č. 43; & č. 43; ] (../ide/media/vs2015_cpp_add_reference.png "vs2015_cpp_add_reference")  

 Můžete nastavit odkaz na následující typy součástmi a službami:    

-   Knihovna tříd rozhraní .NET framework nebo sestavení  

-   Aplikace UWP

-   COM – součásti  

-   Další sestavení nebo knihovny tříd projektů ve stejném řešení  

-   webové služby XML  

## <a name="uwp-app-references"></a>Odkazy na aplikace UWP  

### <a name="project-references"></a>Odkazy na projekt  
 Projekty pro Universal Windows Platform (UWP) můžete vytvořit odkazy na další UWP projekty v řešení, nebo projekty Windows 8.1 nebo binární soubory, za předpokladu, že tyto projekty nepoužívají rozhraní API, která jsou zastaralé v systému Windows 10. Další informace najdete v tématu [přesunutí ze systému Windows 8 Runtime UWP](https://docs.microsoft.com/en-us/windows/uwp/porting/w8x-to-uwp-root).  

 Pokud zvolíte možnost změnit cílový projekty Windows 8.1 na Windows 10, najdete v části [Port, migrace a Upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md)  

### <a name="extension-sdk-references"></a>Reference na rozšíření sady SDK  
 Visual Basic, C#, C++ a JavaScript univerzální platformu Windows (UWP) aplikace, můžete odkazovat rozšíření sady SDK cílených [!INCLUDE[win81](../debugger/includes/win81_md.md)], tak dlouho, dokud tyto rozšíření sady SDK se nedoporučuje používat rozhraní API, která jsou zastaralé v systému Windows 10. Zkontrolujte, zda webu dodavatele rozšíření sady SDK a zjistěte, jestli může být odkazován Microsoft Store projektů cílených UWP.  

 Pokud zjistíte, že rozšíření sady SDK, se na ně odkazovat aplikace není podporována, pak je třeba provést následující kroky:  

1.  Podívejte se na název projektu, který je příčinou chyby. Platformy, na které je cílem vašeho projektu je uvedeno v závorkách vedle názvu projektu. Například **(Windows 8.1) s názvem MyProjectName** znamená, že váš projekt **s názvem MyProjectName** je cílení na platformy verzi [!INCLUDE[win81](../debugger/includes/win81_md.md)].  

2.  Přejděte na webu dodavatele, který vlastní nepodporované Extension SDK a nainstalujte verzi sady SDK rozšíření se závislostmi, které jsou kompatibilní s verzí platformy, na které cílí projektu.  

    > [!NOTE]
    >  Jeden způsob, jak zjistit, jestli má závislosti na dalších sadách SDK rozšíření Extension SDK je restartujte Visual Studio, vytvořte nový projekt aplikace UPW C#, klikněte pravým tlačítkem na projekt a zvolte **přidat odkaz na**, přejděte na **Windows**  přejděte do **rozšíření** dílčí vyberte rozšíření sady SDK a podívejte se na v pravém podokně **správce odkazů**. Pokud má závislosti, budou uvedené existuje.  

    > [!IMPORTANT]
    >  Pokud váš projekt je cílení na Windows 10 a sady SDK rozšíření nainstalovaná v předchozím kroku má závislost na balíček Microsoft Visual C++ Runtime, na verzi Microsoft Visual C++ Runtime balíčku, který je kompatibilní s Windows 10 je v14.0 a je nainstalován pomocí sady Visual Studio.  

3.  Pokud sada SDK rozšíření jste nainstalovali v předchozím kroku má závislosti na dalších sadách SDK rozšíření, přejděte na webu (webům) dodavatele, který vlastní závislosti a nainstalujte verze tyto závislosti, které jsou kompatibilní s verzí platformy vaší je cílení na projektu.  

4.  Restartujte Visual Studio a otevřete v aplikaci.  

5.  Klikněte pravým tlačítkem na **odkazy** uzlu v projektu, který způsobil chybu a zvolte **přidat odkaz na**.  

6.  Klikněte na tlačítko **Windows** kartu a potom **rozšíření** dílčí kartě, zrušte zaškrtnutí políček pro původní sady SDK rozšíření a vyhledávat nové sady SDK rozšíření políček. Click **OK**.  

## <a name="adding-a-reference-at-design-time"></a>Přidání odkazu na v době návrhu  
 Pokud provedete odkaz na sestavení ve vašem projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vyhledá sestavení v následujících umístěních:  

-   Aktuální adresář projektu. (Tyto sestavení můžete najít pomocí **Procházet** karta.)  

-   Další adresáře projektu ve stejném řešení. (Tyto sestavení můžete najít na **projekty** karta.)  

> [!NOTE]
>  Všechny projekty obsahují implicitní odkaz na mscorlib. Projekty Visual Basic obsahují implicitní odkaz na `Microsoft.VisualBasic`.  
>   
>  Všechny projekty v sadě Visual Studio obsahují implicitní odkaz na `System.Core`i v případě `System.Core` se odebere ze seznamu odkazů.  

## <a name="references-to-shared-components-at-run-time"></a>Odkazy na sdílené komponenty v době běhu  
 V době běhu součásti musí být v cestě výstupu projektu nebo v globální mezipaměti sestavení (GAC). Pokud projekt obsahuje odkaz na objekt, který není v jednom z těchto umístění, je nutné zkopírovat odkaz na cestu výstupního projektu při sestavování projektu. <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> Vlastnost určuje, zda tato kopie má být provedena. Pokud je hodnota **True**, odkaz je zkopírován do adresáře projektu při sestavování projektu. Pokud je hodnota **False**, odkaz se nezkopíruje.  

 Pokud nasadíte aplikaci, která obsahuje odkaz na komponentu vlastní, které je registrované v mezipaměti GAC, součást nebude nasazen s aplikací, bez ohledu na to <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> nastavení. V dřívějších verzích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], můžete nastavit <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> vlastnost na odkaz k zajištění, že byla nasazena sestavení. Nyní je třeba ručně přidat sestavení do složky \Bin. To umístí všechny vlastní kód pod kontrolu, snižuje riziko publikování vlastní kód, pomocí kterého nejste obeznámeni.  

 Ve výchozím nastavení <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> je nastavena na **False** Pokud sestavení nebo součást je v globální mezipaměti sestavení nebo komponentu prostředí. Jinak je hodnota nastavená **True**. Odkazy na projekt na projekt jsou vždy nastavená **True**.  

## <a name="referencing-a-project-or-assembly-that-targets-a-different-version-of-the-net-framework"></a>Odkazování na projekt nebo sestavení, které jinou verzi rozhraní .NET Framework  
 Můžete vytvořit aplikace, které odkazují na projekty nebo sestavení, které jinou verzi rozhraní .NET Framework. Například můžete vytvořit aplikace s cílem [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)] který odkazuje na sestavení, která je cílena [!INCLUDE[dnprdnext](../ide/includes/dnprdnext_md.md)]. Pokud vytvoříte projekt, který se zaměřuje na dřívější verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], nelze nastavit odkaz v tomto projektu projekt nebo sestavení s cílem [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)] nebo rozhraní .NET Framework verze 4.  

 Další informace najdete v tématu [cílení na konkrétní verzi rozhraní .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md).  

## <a name="project-to-project-references"></a>Odkazy na projekt na projekt  
 Odkazy na projekt na projekt jsou odkazy na projekty, které obsahují sestavení; můžete vytvořit pomocí **projektu** kartě. Visual Studio můžete najít sestavení při zadána cesta k projektu.  

 Až budete mít na projekt, který vytváří sestavení, by měla odkazovat na projekt a nechcete použít odkaz na soubor (viz níže). Výhodou odkaz na projekt na projekt je, že vytvoří závislost mezi projekty v systému sestavení. Závislé projektu budou vytvořeny, pokud se změnil od posledního odkazujícího projektu. Odkaz na soubor nevytvoří závislost sestavení, takže je možné vytvořit odkazující projekt bez vytváření závislého projektu a odkaz se může stát zastaralé. (To znamená, projekt může odkazovat na dřívější sestavené verze projektu.) Výsledkem může být několik verzí jednoho knihovny DLL se vyžaduje v adresáři bin, což není možné. Když dojde k tomuto konfliktu, zobrazí se zpráva, jako "Upozornění: závislost 'file' v projektu 'project' nelze zkopírovat do běhového adresáře, protože by přepsala odkaz 'file.'". Další informace najdete v tématu [řešení potíží s odkazy na přerušený](../ide/troubleshooting-broken-references.md) a [postupy: vytvoření a odebrání závislostí projektu](../ide/how-to-create-and-remove-project-dependencies.md).  

> [!NOTE]
>  Odkaz na soubor místo odkaz na projekt na projekt se vytvoří, pokud je cílová verze rozhraní .NET Framework projektu jeden verze 4.5 a cílovou verzi sady jiný projekt je verze 2, 3, 3.5 nebo 4.0.  

## <a name="file-references"></a>Odkazy na soubory  
 Odkazy na soubory jsou přímé odkazy na sestavení mimo kontext projekt sady Visual Studio; můžete vytvořit pomocí **Procházet** kartě **správce odkazů**. Odkaz na soubor použijte, pokud jste právě sestavení nebo součást a nemají projekt, který vytvoří jako výstup.  

## <a name="see-also"></a>Viz také  
 [Řešení potíží s poškozenými odkazy](../ide/troubleshooting-broken-references.md)   
 [Postupy: Přidání nebo odebrání odkazů pomocí Správce odkazů](../ide/how-to-add-or-remove-references-by-using-the-reference-manager.md)
