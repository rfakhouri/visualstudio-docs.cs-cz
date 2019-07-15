---
title: Podpora Ngen ve VSIX v. 3 | Dokumentace Microsoftu
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 1472e884-c74e-4c23-9d4a-6d8bdcac043b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 24f1b0a26875bbbf8dfc4ac7db1049f7309d9aa2
ms.sourcegitcommit: 748d9cd7328a30f8c80ce42198a94a4b5e869f26
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67891121"
---
# <a name="ngen-support-in-vsix-v3"></a>Podpora Ngen ve VSIX v. 3

Pomocí sady Visual Studio 2017 a nové VSIX v. 3 manifestu rozšíření (verze 3) formát, teď můžou vývojáři rozšíření "ngen" jejich sestavení v době instalace.

Níže je výňatkem z webu MSDN, která vysvětluje, jaké "ngen" dělá:

>Native Image Generator (*Ngen.exe*) je nástroj zvyšující výkon spravovaných aplikací. *Ngen.exe* vytváří nativní bitové kopie, které jsou soubory obsahující zkompilovaný strojový kód závislý na procesoru a nainstaluje je do mezipaměti nativních bitových kopií v místním počítači. Modul runtime může ke kompilaci původního sestavení použít nativní bitové kopie z mezipaměti namísto kompilátoru JIT (just-in-time).
>
>z [Ngen.exe (Generátor nativních obrázků)](/dotnet/framework/tools/ngen-exe-native-image-generator)

Aby "ngen" sestavení musí být rozšíření VSIX nainstalován "jednotlivé instance vázaná na počítač". Lze povolit zaškrtnutím políčka "all users" `extension.vsixmanifest` návrháře:

![Zkontrolujte všechny uživatele](media/check-all-users.png)

## <a name="how-to-enable-ngen"></a>Povolení technologie Ngen

Pokud chcete povolit ngen pro sestavení, můžete použít **vlastnosti** okna v sadě Visual Studio.

Existují 4 vlastnosti, které je možné nastavit:

1. **Ngen** (Boolean) – Pokud je hodnota true, instalační program sady Visual Studio bude "ngen" sestavení.
2. **Aplikace Ngen** (string) – Ngen nabízí možnost použití aplikace *app.config* souboru, aby bylo možné vyřešit závislosti sestavení. Tato hodnota musí být nastavena na aplikaci jehož *app.config* chcete použít (relativní k adresáři instalace sady Visual Studio).
3. **Architektura Ngen** (výčtu) – architektura pro nativní kompilaci vašeho sestavení. Možnosti jsou:. NotSpecified b. X86 c. X64 d. Všechny
4. **Priorita Ngen** (celé číslo mezi 1 a 3) – úroveň The Ngen Priority je popsána v [úrovně priority Ngen.exe](/dotnet/framework/tools/ngen-exe-native-image-generator#priority-levels).

Tady se můžete podívat na **vlastnosti** okno v akci:

![v dialogovém okně Vlastnosti Ngen](media/ngen-in-properties.png)

Metadata se přidá do projektu odkaz v projektu VSIX *.csproj* souboru:

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
    <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
    <Name>ClassLibrary1</Name>
    <Ngen>True</Ngen>
    <NgenApplication>vsn.exe</NgenApplication>
    <NgenArchitecture>X86</NgenArchitecture>
    <NgenPriority>2</NgenPriority>
</ProjectReference>
```

> [!NOTE]
> Pokud dáváte přednost můžete přímo, upravte soubor csproj.

## <a name="extra-information"></a>Další informace

Vlastnosti návrháře změny se aplikují na víc než jenom odkazy projektu; můžete nastavit metadata Ngen pro položky v rámci projektu také (pomocí stejných metod, popsané výše), dokud položky jsou sestavení .NET.