---
title: Podpora Ngen ve VSIX v3 | Microsoft Docs
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1472e884-c74e-4c23-9d4a-6d8bdcac043b
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 15277f0a1038e43bb316d604cbc415da4a5d80bd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ngen-support-in-vsix-v3"></a>Podpora Ngen ve VSIX v3

Visual Studio 2017 a nové v3 VSIX manifest rozšíření (verze 3) formátu, můžete je rozšíření vývojáři teď "ngen" jejich sestavení v době instalace.

Níže je výňatek ze MSDN, která vysvětluje, co "ngen" nemá:

>Generátor nativních bitových kopií (Ngen.exe) je nástroj zvyšující výkon spravovaných aplikací. Nástroj Ngen.exe vytváří nativní bitové kopie, což jsou soubory obsahující zkompilovaný strojový kód specifický pro procesor, a instaluje je do mezipaměti nativních bitových kopií v místním počítači. Modul runtime může ke kompilaci původního sestavení použít nativní bitové kopie z mezipaměti namísto kompilátoru JIT (just-in-time).
>
>z [Ngen.exe (Generátor nativních obrázků)](https://msdn.microsoft.com/en-us/library/6t9t5wcf(v=vs.110).aspx)

Aby "ngen" na sestavení musí být VSIX nainstalován "jednotlivých instancí na počítač". To může být povolena zaškrtnutím políčka "všechna users" v Návrháři extension.vsixmanifest:

![Zkontrolujte všechny uživatele](media/check-all-users.png)

## <a name="how-to-enable-ngen"></a>Postup povolení Ngen

Chcete-li povolit ngen pro sestavení, můžete použít **vlastnosti** oken v sadě Visual Studio.

Nejsou k dispozici 4 vlastnosti, které lze nastavit:

1. **Ngen** (Boolean) - li nastavena hodnota true, instalační program sady Visual Studio bude "ngen" sestavení.
2. **Aplikace Ngen** (řetězec) Ngen poskytuje možnost použití souboru app.config aplikace za účelem vyřešení závislostí sestavení. Tato hodnota by měla aplikace jejichž app.config, kterou chcete použít (relativní vůči adresáři instalace sady Visual Studio).
3. **Architektura Ngen** (výčtu) – architektura při kompilaci nativně sestavení. Možnosti jsou:. NotSpecified b. X86 c. X64 d. Všechny
4. **Priorita Ngen** (celé číslo mezi 1 a 3) - úroveň Priority Ngen je popsána v [úroveň Priority Ngen.exe](https://msdn.microsoft.com/en-us/library/6t9t5wcf(v=vs.110).aspx#Anchor_3).

Tady je podívejte se na **vlastnosti** okno v akci:

![Ngen ve vlastnostech](media/ngen-in-properties.png)

Metadata se přidá do projektu odkaz uvnitř souboru .csproj projektů VSIX:

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

 >**Poznámka:** můžete upravit souboru .csproj přímo, pokud dáváte přednost.

## <a name="extra-information"></a>Další informace

Změny vlastností návrháře platí pro více než jen odkazů projektu; můžete nastavit Ngen metadata pro položky v rámci projektu také (pomocí stejné metody popsané výše) dlouho položky jsou sestavení .NET.