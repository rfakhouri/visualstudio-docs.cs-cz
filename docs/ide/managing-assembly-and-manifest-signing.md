---
title: Správa podepsání sestavení a manifestu
ms.date: 02/17/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- manifests [Visual Studio]
- signing manifests [Visual Studio]
- application manifests [Visual Studio]
- assemblies [Visual Studio], signing
ms.assetid: 6c1ef36b-25f7-4ad0-b29a-51801b7a5420
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bef64670c3c2631e779fda0f48810ce502db72b1
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844424"
---
# <a name="manage-assembly-and-manifest-signing"></a>Správa podepsání sestavení a manifestu

Softwarová součást podpis silného názvu poskytuje identitu globálně jedinečný. Silné názvy jsou použity k zajištění, že sestavení nemůže být falešné jiným uživatelem a zajistit, že závislosti součástí a konfigurace příkazy mapování na správné součásti a verze komponenty.

Silné jméno se skládá z identity sestavení (jednoduchý textový název, číslo verze a informace o jazykové verzi), plus token veřejného klíče a digitální podpis.

Informace o podepisování sestavení v projektech Visual Basic a C# najdete v tématu [vytvoření a použití sestavení se silným názvem](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).

Informace o podepisování sestavení v projektech Visual C++ najdete v tématu [sestavení se silným názvem (C + +/ CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli).

> [!NOTE]
> Podpis silného názvu neposkytuje ochranu proti zpětnou sestavení. Chcete-li chránit proti zpětnou, přečtěte si téma [Dotfuscatoru Community Edition (CE)](dotfuscator/index.md).

## <a name="asset-types-and-signing"></a>Typy Asset a podepisování

Můžete se přihlásit manifestů aplikace a sestavení .NET:

- spustitelné soubory (*.exe*)

- manifesty aplikace (*. exe.manifest*)

- manifesty nasazení (*.application*)

- sdílená součást sestavení (*.dll*)

Zaregistrujte následující typy asset:

1. Sestavení, pokud chcete nasadit do globální mezipaměti sestavení (GAC).

2. Manifesty aplikace a nasazení ClickOnce. Visual Studio umožňuje podepisování ve výchozím nastavení pro tyto aplikace.

3. Primární spolupracující sestavení, které se používají pro interoperabilita modelů COM. Nástroj TLBIMP vynucuje silné názvy při vytváření primárních sestavení vzájemné spolupráce z knihovny typů COM.

Obecně platí by neměl podepsat spustitelné soubory. Silně pojmenované součást nesmí odkazovat na komponentu jiný silným názvem, který je nasazen s aplikací. Visual Studio není podepsat spustitelné soubory aplikace, ale místo toho přihlásí manifestu aplikace, který odkazuje na spustitelný soubor s názvem příliš slabé. Vyhněte se podepisování součásti, které jsou privátní k vaší aplikaci, protože podpis může být obtížné spravovat závislosti.

## <a name="how-to-sign-an-assembly-in-visual-studio"></a>Postup podepsání sestavení v sadě Visual Studio

Podepsání aplikace nebo součásti pomocí **podpisování** karta v okně Vlastnosti projektu (klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a vyberte **vlastnosti**, nebo typ **projektu vlastnosti** v **Snadné spuštění** okno, nebo klikněte na tlačítko **Alt**+**Enter**uvnitř **Průzkumníku řešení** okno). Vyberte **podpisování** a potom vyberte **podepsání sestavení** zaškrtávací políčko.

Zadejte soubor klíče. Pokud se rozhodnete vytvořit nový soubor klíče, jsou vždy vytváří nové soubory klíčů v *.pfx* formátu. Potřebujete jméno a heslo pro nový soubor.

> [!WARNING]
> Vždy byste měli chránit váš soubor klíče s heslem někdo zabránit jeho použití. Také můžete zabezpečit vaše klíče pomocí poskytovatelů nebo úložiště certifikátů.

Může taky ukazovat na klíč, který jste už vytvořili. Další informace o vytváření klíčů najdete v tématu [vytvoření páru veřejného a privátního klíče RSA](/dotnet/framework/app-domains/how-to-create-a-public-private-key-pair).

Pokud máte pouze přístup s veřejným klíčem, můžete použít zpoždění podepsání odložení přiřazení klíč. Povolit zpoždění podepsání výběrem **zpoždění podepsání** zaškrtávací políčko. Zpoždění podepsané projektu nefunguje a nelze ji ladění. Však můžete přeskočit ověření během vývoje pomocí [nástroj pro silný název Sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) s `-Vr` možnost.

Informace o podepisování manifestů najdete v tématu [postupy: podepsání manifestů aplikace a nasazení](../ide/how-to-sign-application-and-deployment-manifests.md).

## <a name="see-also"></a>Viz také:

- [Sestavení se silným názvem](/dotnet/framework/app-domains/strong-named-assemblies)
- [Sestavení se silným názvem (C + +/ CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli)
