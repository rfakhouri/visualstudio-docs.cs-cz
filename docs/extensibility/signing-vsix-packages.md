---
title: Podepisování balíčků VSIX | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 710cc523cdd01ad431572860ace9b06af3cff418
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66332086"
---
# <a name="signing-vsix-packages"></a>Podepisování balíčků VSIX
Rozšíření sestavení není nutné před jejich spuštěním v sadě Visual Studio, ale je dobrým zvykem Uděláte to tak.

 Pokud chcete zabezpečit vaše rozšíření a ujistěte se, že někdo nemanipuloval s, můžete přidat digitálního podpisu balíčku VSIX. Při podepsání VSIX instalátor VSIX se zobrazí zprávu s oznámením, že není podepsané, plus další informace o podpisu samotný. Pokud obsah VSIX byly změněny a VSIX nebyl znovu podepsán, instalátor VSIX se zobrazí, že podpis není platný. Instalace se zastaví, ale uživatel je upozorněn.

> [!IMPORTANT]
> Od verze Visual Studio 2015, balíčků VSIX, které jsou podepsány pomocí nic jiného než SHA256 šifrování bude považovat za s neplatným podpisem. Instalace VSIX není blokován, ale uživatel zobrazí upozornění.

## <a name="signing-a-vsix-with-vsixsigntool"></a>Podepsání souboru VSIX pomocí VSIXSignTool
 Je SHA256 šifrování podepisování nástroj dostupný z [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) na nuget.org na [VsixSignTool](http://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool).

#### <a name="to-use-the-vsixsigntool"></a>Použít VSIXSignTool

1. Přidejte do projektu VSIX.

2. Klikněte pravým tlačítkem na uzel projektu v Průzkumníku řešení vyberte **přidat &#124; spravovat balíčky NuGet**.  Další informace o NuGet a přidání NuGet naleznete v tématu balíčky [dokumentace pro NuGet](/NuGet) a [uživatelské rozhraní Správce balíčků](/NuGet/Tools/Package-Manager-UI) témata.

3. Vyhledejte VSIXSignTool z VisualStudioExtensibility a nainstalujte balíček NuGet.

4. Nyní můžete spustit VSIXSignTool z umístění místního balíčky projektu. Najdete nápovědu k příkazovému řádku nástroje pro podepisování scénář (VSIXSignTool.exe /?).

   Třeba když chcete přihlásit s heslem chráněná soubor certifikátu:

   VSIXSignTool.exe sign /f \<certfile> /p \<password> \<VSIXfile>

## <a name="see-also"></a>Viz také
- [Odesílání rozšíření sady Visual Studio](../extensibility/shipping-visual-studio-extensions.md)
