---
title: 'Postupy: Konfigurace cílů a úloh | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
ms.assetid: 92814100-392a-471d-96fd-e26f637d6cc2
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c8ef52638858160822fcc271a53513b130afc3f4
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440042"
---
# <a name="how-to-configure-targets-and-tasks"></a>Postupy: Konfigurace cílů a úloh
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vybrané úlohy nástroje MSBuild může nastaven na spouštění v prostředí, které cílí, bez ohledu na prostředí, které vývojovém počítači. Například pokud používáte 64bitový počítač k sestavení aplikace pro danou architekturu cíle 32-bit, vybrané úlohy se spouštějí v 32bitový proces.  
  
> [!NOTE]
> Pokud úloha sestavení je napsaný v jazyce .NET, jako je Visual C# nebo Visual Basic a nepoužívá nativní prostředky nebo nástroje, pak se spustí v libovolném kontextu cílového bez přizpůsobení.  
  
## <a name="usingtask-attributes-and-task-parameters"></a>Usingtask – atributy a parametry úlohy  
 Následující `UsingTask` ovlivňují všechny operace úloh v procesu sestavení konkrétní atributy:  
  
- `Runtime` Atribut, pokud jsou k dispozici, nastaví společné jazykové verzi modulu runtime (CLR) a můžete provést některou z těchto hodnot: `CLR2`, `CLR4`, `CurrentRuntime`, nebo `*` (žádné runtime).  
  
- `Architecture` Atribut, pokud jsou k dispozici, nastaví platformy a počtu bitů a můžete provést jednu z těchto hodnot: `x86`, `x64`, `CurrentArchitecture`, nebo `*` (všechny architektury).  
  
- `TaskFactory` Atribut, pokud jsou k dispozici, nastaví továrny úloh, která vytvoří a spustí instanci úlohy a přijímá pouze hodnotu `TaskHostFactory`. Další informace najdete v části továrny úloh dále v tomto dokumentu.  
  
```  
<UsingTask TaskName="SimpleTask"   
   Runtime="CLR2"  
   Architecture="x86"  
   AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v3.5.dll" />  
```  
  
 Můžete také použít `MSBuildRuntime` a `MSBuildArchitecture` parametry se mají nastavit cílový kontext jednotlivé úlohy.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <SimpleTask MSBuildRuntime="CLR2" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
```  
  
 Předtím, než MSBuild spustí úlohu, vyhledá odpovídající `UsingTask` , který má stejný cílový kontext.  Parametry, které jsou určené v `UsingTask` , ale ne v odpovídající úlohy jsou považovány za odpovídat.  Parametry zadané v úloze, ale ne v odpovídající `UsingTask` jsou také považovány za odpovídat. Pokud nejsou zadány hodnoty parametrů buď `UsingTask` nebo úlohou, výchozí hodnoty `*` (žádné parametry).  
  
> [!WARNING]
> Pokud více než jeden `UsingTask` existuje a mít odpovídající `TaskName`, `Runtime`, a `Architecture` atributy, posledním blokem, který se má vyhodnotit nahradí ostatní.  
  
 Pokud parametry nejsou nastavené na úkolu, MSBuild, pokusí se najít `UsingTask` , který odpovídá tyto parametry nebo alespoň, není konfliktu s nimi.  Více než jeden `UsingTask` můžete určit cílový kontext stejnou úlohu.  Úloha, která má jinou spustitelné soubory pro jiné cílové prostředí může vypadat například tento:  
  
```  
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
 Před spuštěním úkolu, zkontroluje MSBuild, zda je určený pro spouštění v aktuálním kontextu softwaru.  Pokud úloha je určena, nástroj MSBuild ji předá AssemblyTaskFactory, který se spouští v aktuálním procesu; v opačném případě se předá MSBuild TaskHostFactory, který se spouští úloha v procesu, který odpovídá cílový kontext úkolu. I v případě, že aktuální kontext a cílový kontext shodují, můžete vynutit spuštění úlohy mimo proces (pro izolaci, zabezpečení nebo z jiných důvodů) tak, že nastavíte `TaskFactory` k `TaskHostFactory`.  
  
```  
<UsingTask TaskName="MisbehavingTask"   
   TaskFactory="TaskHostFactory"  
   AssemblyFile="$(MSBuildToolsPath)\MyTasks.dll">  
</UsingTask>  
```  
  
## <a name="phantom-task-parameters"></a>Parametry fiktivní úlohy  
 Další parametry úlohy, jako jsou `MSBuildRuntime` a `MSBuildArchitecture` lze nastavit z vlastností sestavení.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <PropertyGroup>  
      <FrameworkVersion>3.0</FrameworkVersion>  
   </PropertyGroup>  
   <Target Name="MyTarget">  
      <SimpleTask MSBuildRuntime="$(FrameworkVerion)" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
```  
  
 Na rozdíl od jiných parametry úlohy `MSBuildRuntime` a `MSBuildArchitecture` nejsou zřejmé vlastní úloha.  Zapsat úlohu, která ví o kontextu, ve které běží, musíte otestovat kontextu voláním rozhraní .NET Framework nebo pomocí sestavení vlastností předávat informace o kontextu prostřednictvím jiné parametry úlohy.  
  
> [!NOTE]
> `UsingTask` atributy lze nastavit z vlastnosti sadu nástrojů a prostředí.  
  
 `MSBuildRuntime` a `MSBuildArchitecture` parametry poskytují nejflexibilnější způsob, jak nastavit cílový kontext, ale také nejvíc omezenou v oboru.  Na jedné straně protože jsou nastaveny na samotné instanci úlohy a nebudou vyhodnoceny, dokud není spuštěn úkol, následně mohli proniknout jejich hodnoty z vlastnosti, které jsou k dispozici na zkušební dobu a čas sestavení v plném rozsahu.  Na druhé straně tyto parametry platí jenom pro konkrétní instanci úlohy v konkrétnímu cíli.  
  
> [!NOTE]
> Parametry úlohy se vyhodnocují v rámci nadřazeného uzlu, nejsou v rámci hostitele úloh. Proměnné prostředí, které se modul runtime nebo architektura závislé (jako je například umístění programových souborů) se vyhodnotí na hodnotu, která odpovídá nadřazený uzel.  Ale pokud stejnou proměnnou prostředí přečte přímo úkol, je správně se vyhodnotí v kontextu bude hostitel úloh.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace cílů a úloh](../msbuild/configuring-targets-and-tasks.md)
