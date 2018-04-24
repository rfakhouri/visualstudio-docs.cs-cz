---
title: 'Postupy: konfigurace cílů a úloh | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
ms.assetid: 92814100-392a-471d-96fd-e26f637d6cc2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7a09f2ec1af511cb789f2101e2df0a675dd065e8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-configure-targets-and-tasks"></a>Postupy: Konfigurace cílů a úloh
Vybrané úlohy nástroje MSBuild může být nastaveny na spouštění v prostředí, ve kterém se zaměřit, bez ohledu na prostředí vývojovém počítači. Například pokud používáte 64bitový počítač pro vytvoření této architektuře cíle 32bitové aplikace, vybrané úlohy se spouštějí v 32bitový proces.  
  
> [!NOTE]
>  Pokud úlohu sestavení je napsán v jazyce platformy .NET, jako je například Visual C# nebo Visual Basic a nepoužívá nativní prostředky nebo nástroje, se spustí v kontextu žádné cílové bez přizpůsobení.  
  
## <a name="usingtask-attributes-and-task-parameters"></a>Usingtask – atributy a parametry úlohy  
 Následující `UsingTask` atributy vliv na všechny operace v procesu sestavení konkrétní úlohy:  
  
-   `Runtime` Atribut, pokud existuje, nastaví společné jazykové verzi modulu runtime (CLR) a může přijmout jeden z těchto hodnot: `CLR2`, `CLR4`, `CurrentRuntime`, nebo `*` (všechny runtime).  
  
-   `Architecture` Atribut, pokud existuje, nastaví platformy a počtu bitů a můžete provést jednu z těchto hodnot: `x86`, `x64`, `CurrentArchitecture`, nebo `*` (všechny architektura).  
  
-   `TaskFactory` Atribut, pokud existuje, nastaví objekt pro vytváření úloh vytvoří a spustí instance úlohy a přijímá pouze hodnotu `TaskHostFactory`. Další informace najdete v části objekty pro vytváření úloh později v tomto dokumentu.  
  
```xml  
<UsingTask TaskName="SimpleTask"   
   Runtime="CLR2"  
   Architecture="x86"  
   AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v3.5.dll" />  
```  
  
 Můžete také `MSBuildRuntime` a `MSBuildArchitecture` parametry nastavit cílový kontext jednotlivé úlohy.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <SimpleTask MSBuildRuntime="CLR2" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
```  
  
 Před spuštěním nástroje MSBuild úlohu, vypadá odpovídající `UsingTask` má stejné cílový kontext.  Parametry, které jsou určené v `UsingTask` , ale ne v odpovídající úlohy se považují za lze porovnat.  Parametry, které jsou zadány v úloze, ale ne v odpovídající `UsingTask` jsou také považovány za lze porovnat. Pokud nejsou zadané hodnoty parametru buď `UsingTask` nebo úlohy, výchozí hodnoty `*` (libovolný parametr).  
  
> [!WARNING]
>  Pokud je více než jeden `UsingTask` existuje a mají odpovídající `TaskName`, `Runtime`, a `Architecture` atributy, naposledy, který se má vyhodnotit nahrazuje jiné.  
  
 Pokud parametry nejsou nastavené v úloze, MSBuild pokusí se najít `UsingTask` , odpovídá tyto parametry nebo, minimálně, není v konfliktu s nimi.  Více než jeden `UsingTask` můžete zadat cílový kontext té samé úlohy.  Úloha, která má jiný spustitelné soubory pro různé cílové prostředí může vypadat například tato:  
  
```xml  
<UsingTask TaskName="MyTool"   
   Runtime="CLR2"  
   Architecture="x86"  
   AssemblyFile="$(MyToolsPath)\MyTool.v2.0.dll" />  
  
<UsingTask TaskName="MyTool"   
   Runtime="CLR4"  
   Architecture="x86"  
   AssemblyFile="$(MyToolsPath)\MyTool.4.0.dll" />  
  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <MyTool MSBuildRuntime="CLR2" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
  
```  
  
## <a name="task-factories"></a>Továrny úloh  
 Před spuštěním úlohy, MSBuild zkontroluje, zda je určený ke spuštění v aktuálním kontextu softwaru.  Pokud úloha je určena, se MSBuild předá AssemblyTaskFactory, který se spouští v aktuálním procesu; MSBuild, jinak předá úlohu TaskHostFactory, který se spouští úlohy v procesu, který odpovídá cílový kontext. I v případě, že aktuální kontext a cílový kontext shodují, můžete vynutit spuštění úlohy out-of-process (pro izolaci, zabezpečení nebo z jiných důvodů) nastavením `TaskFactory` k `TaskHostFactory`.  
  
```xml  
<UsingTask TaskName="MisbehavingTask"   
   TaskFactory="TaskHostFactory"  
   AssemblyFile="$(MSBuildToolsPath)\MyTasks.dll">  
</UsingTask>  
```  
  
## <a name="phantom-task-parameters"></a>Parametry fiktivní úlohy  
 Jako další parametry úlohy `MSBuildRuntime` a `MSBuildArchitecture` lze nastavit z vlastností sestavení.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <PropertyGroup>  
      <FrameworkVersion>3.0</FrameworkVersion>  
   </PropertyGroup>  
   <Target Name="MyTarget">  
      <SimpleTask MSBuildRuntime="$(FrameworkVerion)" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
```  
  
 Na rozdíl od jiných parametry úlohy `MSBuildRuntime` a `MSBuildArchitecture` nejsou zřejmé, vlastní úloha.  Zápis úlohu, která má informace o kontextu, ve které běží, musíte otestovat kontextu voláním rozhraní .NET Framework nebo pomocí sestavení vlastností předávat informace o kontextu prostřednictvím jiné parametry úlohy.  
  
> [!NOTE]
>  `UsingTask` atributy lze nastavit z vlastností sada nástrojů a prostředí.  
  
 `MSBuildRuntime` a `MSBuildArchitecture` parametry představují nejpružnější způsob, jak nastavit cílový kontext, ale také nejvíc omezenou v oboru.  Na jedné straně protože jsou nastaveny v samotné instanci úlohy a nebudou vyhodnoceny, dokud není spuštěn úkol, jejich odvozovat jejich hodnota z úplné oboru vlastností, které jsou k dispozici v době vyhodnocení a čase vytvoření buildu.  Na druhé straně tyto parametry platí pouze pro konkrétní instanci úloha v konkrétní cílový.  
  
> [!NOTE]
>  Parametry úlohy jsou vyhodnocovány v rámci nadřazeného uzlu, není v kontextu hostitele úloh. Proměnné prostředí, které jsou runtime nebo architektura závislé (jako je například umístění souborů programu) vyhodnotí na hodnotu, která odpovídá nadřazený uzel.  Však stejnou proměnnou prostředí je přečtení přímo úlohou, je správně vyhodnotí v rámci hostitele úloh.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace cílů a úloh](../msbuild/configuring-targets-and-tasks.md)
