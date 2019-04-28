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
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7d2da473d201ff02b65262190158da1818bb1816
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63434573"
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
