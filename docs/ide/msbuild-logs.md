---
title: Řešení potíží a vytvořit protokoly pro nástroj MSBuild problémy
ms.date: 06/27/2019
ms.topic: conceptual
helpviewer_keywords:
- msbuild logs"
author: mikeblome
ms.author: mblome
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.description: Generate build logs for msbuild projects to collect helpful information when troubleshooting issues.
ms.openlocfilehash: c3db56ac7ea60ce88beae6698c974ac91373ed00
ms.sourcegitcommit: 6f7a740750b2cd17ea2275c3d046caebc9782917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67518238"
---
# <a name="troubleshoot-and-create-logs-for-msbuild-problems"></a>Řešení potíží a vytvořit protokoly pro nástroj MSBuild problémy

Následující postupy můžete pomoci při diagnostice problémů se sestavením projektu sady Visual Studio a v případě potřeby vytvořte protokolu posílat do Microsoftu pro šetření.

## <a name="a-property-value-is-ignored"></a>Hodnota vlastnosti se ignoruje.

Pokud se zdá být nastavena na určitou hodnotu vlastnosti projektu, ale nemá žádný vliv na sestavení, postupujte podle těchto kroků:

1. Otevřete Visual Studio Developer Command Prompt, která odpovídá vaší verzi sady Visual Studio.
1. Spusťte následující příkaz, po nahrazení hodnot k cesta řešení, konfiguraci a název projektu:

    ```cmd
    msbuild /p:SolutionDir="c:\MySolutionDir\";Configuration="MyConfiguration";Platform="Win32" /pp:out.xml MyProject.vcxproj
    ```

    Tento příkaz vytvoří soubor projektu msbuild "předzpracovaná" (out.xml). Můžete vyhledat tento soubor pro určité vlastnosti chcete zobrazit, kde je definován.

Poslední definice vlastnosti je co spotřebovává sestavení. Pokud je vlastnost nastavena dvakrát, druhá hodnota přepíše první. Také nástroj MSBuild vyhodnotí projekt v několik průchodů:

- Element PropertyGroups a importů
- ItemDefinitionGroups
- ItemGroups
- Cíle

Proto uvedeny následovně:

```xml
<PropertyGroup>
   <MyProperty>A</MyProperty>
</PropertyGroup>
<ItemGroup>
   <MyItems Include="MyFile.txt"/>
</ItemGroup>
<ItemDefinitionGroup>
  <MyItems>
      <MyMetadata>$(MyProperty)</MyMetadata>
  </MyItems>
</ItemDefinitionGroup>
<PropertyGroup>
   <MyProperty>B</MyProperty>
</PropertyGroup>
```

Hodnota "MyMetadata". "MyFile.txt" položky se vyhodnotí na "B" během sestavování (ne "A" a není prázdný)

## <a name="incremental-build-is-building-more-than-it-should"></a>Přírůstkové sestavení vytváří více než by měl

Pokud nástroj MSBuild je zbytečně znovu sestavit projekt nebo položku projektu, vytvořte protokolu podrobné nebo binárního sestavení. Můžete hledat v protokolu pro soubor, který vystavění nebo zkompilovány zbytečně. Výstup bude vypadat přibližně takto:

```output
  Task "CL"

  Using cached input dependency table built from:

  F:\test\Project1\Project1\Debug\Project1.tlog\CL.read.1.tlog

  Outputs for F:\TEST\PROJECT1\PROJECT1\PROJECT1.CPP:
  F:\TEST\PROJECT1\PROJECT1\DEBUG\PROJECT1.OBJ
  Project1.cpp will be compiled because F:\TEST\PROJECT1\PROJECT1\PROJECT1.H was modified at 6/5/2019 12:37:09 PM.

  Outputs for F:\TEST\PROJECT1\PROJECT1\PROJECT1.CPP:
  F:\TEST\PROJECT1\PROJECT1\DEBUG\PROJECT1.OBJ

  Write Tracking Logs:
  Debug\Project1.tlog\CL.write.1.tlog
```

Pokud vytváříte ve integrovaném vývojovém prostředí sady Visual Studio (s podrobností podrobný výstup okna), **okno výstup** Zobrazí důvod, proč každý projekt není aktuální:

```output
1>------ Up-To-Date check: Project: Project1, Configuration: Debug Win32 ------

1>Project is not up-to-date: build input 'f:\test\project1\project1\project1.h' was modified after the last build finished.
```

## <a name="create-a-binary-msbuild-log"></a>Vytvořit msbuild binární protokol

1. Otevřete příkazový řádek pro vývojáře pro vaši verzi sady Visual Studio
1. Z příkazového řádku spusťte následující příkazy. (Nezapomeňte použít skutečné projektu a konfigurační hodnoty.):

    ```cmd
    Msbuild /p:Configuration="MyConfiguration";Platform="x86" /bl MySolution.sln
    ```

    or

    ```cmd
    Msbuild /p:/p:SolutionDir="c:\MySolutionDir\";Configuration="MyConfiguration";Platform="Win32" /bl MyProject.vcxproj
    ```

Vytvoří se soubor Msbuild.binlog do adresáře, který jste spustili nástroj MSBuild z. Můžete zobrazit a vyhledat pomocí [Msbuild strukturovaných Log Viewer](http://www.msbuildlog.com/).

## <a name="create-a-detailed-log"></a>Vytvořit podrobný protokol

1. V hlavní nabídce sady Visual Studio, přejděte na **nástroje** > **možnosti** > **projekty a řešení** >**sestavení a spusťte**.
1. Nastavte **podrobností buildu projektu nástroje Msbuild** k **podrobné** v obou polích se seznamem. Horní jeden ovládací prvky podrobností sestavení **okno výstup** a druhý určuje podrobnost sestavení v \<projectname\>souboru .log, vytvořené ve zprostředkujícím adresáři každý projekt během sestavení.
1. Z příkazového řádku pro vývojáře Visual Studio zadejte jeden z těchto příkazů, kde nahradíte skutečnými hodnotami cestu a konfigurace:

    ```cmd
    Msbuild /p:Configuration="MyConfiguration";Platform="x86" /fl MySolution.sln 
    ```

    or

    ```cmd
    Msbuild /p:/p:SolutionDir="c:\MySolutionDir\";Configuration="MyConfiguration";Platform="Win32" /fl MyProject.vcxproj
    ```

    Vytvoří se soubor s příponou Msbuild.log do adresáře, který jste spustili nástroj msbuild z.
