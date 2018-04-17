---
title: Správa sestavení a podepsání manifestu | Microsoft Docs
ms.custom: ''
ms.date: 02/17/2017
ms.technology:
- vs-ide-general
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
ms.openlocfilehash: 2104ea0a86b351d0300bb7327c338dfcb0cd1818
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="managing-assembly-and-manifest-signing"></a>Správa sestavení a podepsání manifestu
Softwarová součást podpis silného názvu poskytuje identitu globálně jedinečný. Silné názvy jsou použity zaručit, že sestavení nemůže být falešné jiným uživatelem a zajistit závislosti součástí a příkazy konfigurace, které se mapují na správný komponentu a verze komponenty.  
  
 Silné jméno se skládá z identity sestavení (jednoduchý textový název, číslo verze a informace o jazykové verzi), plus token veřejného klíče a digitální podpis.  
  
 Informace o podepisování sestavení v projektech Visual Basic a C# najdete v tématu [vytvoření a použití sestavení](http://msdn.microsoft.com/Library/ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9).  
  
 Informace o podepisování sestavení v projektech Visual C++ najdete v tématu [sestavení se silným názvem (podepisování sestavení) (C + +/ CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli).  

> [!NOTE]
>  Podpis silného názvu neposkytuje ochranu proti zpětnou sestavení.  Chcete-li chránit proti zpětnou, přečtěte si téma [Dotfuscatoru Community Edition (CE)](dotfuscator/index.md).
  
## <a name="asset-types-and-signing"></a>Typy Asset a podepisování  
 Můžete si manifestů aplikace a sestavení .NET. Patří mezi ně například:  
  
-   spustitelné soubory (.exe)  
  
-   manifesty aplikace (. exe.manifest)  
  
-   manifesty nasazení (.application)  
  
-   sdílená součást sestavení (.dll)  
  
Následující typy asset, musíte se odhlásit:  
  
1.  Sestavení, pokud chcete nasadit do globální mezipaměti sestavení (GAC).  
  
2.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesty aplikace a nasazení. Visual Studio umožňuje podepisování ve výchozím nastavení pro tyto aplikace.  
  
3.  Primární spolupracující sestavení, které se používají pro interoperabilita modelů COM. Nástroj TLBIMP vynucuje silné názvy při vytváření primárních sestavení vzájemné spolupráce z knihovny typů COM.  
  
Obecně by neměl podepsat spustitelné soubory. Silně pojmenované součást nesmí odkazovat na komponentu jiný silným názvem, který je nasazen s aplikací. Visual Studio není podepsat spustitelné soubory aplikace, ale místo toho přihlásí manifestu aplikace, který odkazuje na spustitelný soubor s názvem příliš slabé. Obecně byste neměli podepisování součásti, které jsou privátní k vaší aplikaci, protože podpis může být obtížné spravovat závislosti.  
  
## <a name="how-to-sign-an-assembly-in-visual-studio"></a>Postup podepsání sestavení v sadě Visual Studio  
 Podepsání aplikace nebo součásti pomocí **podpisování** karta v okně Vlastnosti projektu (klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a vyberte **vlastnosti**, nebo typ **projektu vlastnosti** v **Snadné spuštění** okno, nebo stiskněte klávesovou zkratku ALT + zadejte uvnitř **Průzkumníku řešení** okno). Vyberte **podpisování** a potom vyberte **podepsání sestavení** zaškrtávací políčko.  
  
 Zadejte soubor klíče. Pokud se rozhodnete vytvořit nový soubor klíče, Všimněte si, že se vždy vytváří nové soubory klíčů ve formátu .pfx. Potřebujete jméno a heslo pro nový soubor.  
  
> [!WARNING]
>  Vždy byste měli chránit váš soubor klíče s heslem někdo zabránit jeho použití. Také můžete zabezpečit vaše klíče pomocí poskytovatelů nebo úložiště certifikátů.  
  
 Může taky ukazovat na klíč, který jste už vytvořili. Další informace o vytváření klíčů najdete v tématu [postupy: vytvoření pár veřejného a privátního klíče](/dotnet/framework/app-domains/how-to-create-a-public-private-key-pair).  
  
 Pokud máte přístup jenom k veřejný klíč, můžete použít zpoždění podepsání odložení přiřazení klíč. Povolit zpoždění podepsání výběrem **zpoždění podepsání** zaškrtávací políčko. Zpoždění podepsané projektu se nespustí a nelze ji ladění. Však můžete přeskočit ověření během vývoje pomocí [Sn.exe (nástroj silným názvem)](/dotnet/framework/tools/sn-exe-strong-name-tool) s `-Vr` možnost.  
  
 Informace o podepisování manifestů najdete v tématu [postupy: přihlášení aplikace a manifesty nasazení](../ide/how-to-sign-application-and-deployment-manifests.md).  
  
## <a name="see-also"></a>Viz také  
 [Sestavení se silným názvem](/dotnet/framework/app-domains/strong-named-assemblies)   
 [Sestavení se silným názvem (podepisování sestavení) (C++/CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli)