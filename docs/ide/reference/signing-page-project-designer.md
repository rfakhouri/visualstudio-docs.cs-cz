---
title: Stránka Podepisování, návrhář projektu (C#)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.AddNewStrongNameKey
- ResolveKeySource.KeyFileForSignAssemblyNotImported
- vb.ProjectPropertiesSigning.ChangePasswordDialog
- ResolveKeySource.KeyFileForManifestNotImported
- vb.ProjectPropertiesSigning
- vb.ProjectPropertiesSigning.PasswordNeededDialog
- vb.ProjectPropertiesSigning.PfxPasswordDialog
helpviewer_keywords:
- Project Designer, Signing page
- Signing page in Project Designer
ms.assetid: dab3ba13-2f92-4827-92bd-1be3c35bc48b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 28c6b2a9fa289bacaad783f70cd85365b7b0628f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="signing-page-project-designer"></a>Stránka Podepisování, návrhář projektu (C#)
Použití **podpisování** stránky **Návrhář projektu** k podepsání manifestů aplikace a nasazení a také k podepsání sestavení (podpis silného názvu).

 Všimněte si, že podepisování manifestů aplikace a nasazení je proces, liší od podepisování sestavení, i když obě úlohy se na **podpisování** stránky.

 Také uložení informací o souboru klíče se liší pro podepsání manifestu a podepsání sestavení. Podepsání manifestu, informace o klíči ukládají do vašeho počítače kryptografického úložiště databáze a úložiště certifikátů aktuálního uživatele systému Windows. Podepisování sestavení informace o klíči ukládají pouze v kryptografických úložiště databáze.

 Pro přístup k **podpisování** vyberte uzel projektu v **Průzkumníku řešení**a pak klikněte na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **podpisování** kartě.

## <a name="application-and-deployment-manifest-signing"></a>Podepisování manifestů aplikace a nasazení
 **Podepisování manifestů ClickOnce** zaškrtávací políčko

 Výběrem tohoto zaškrtávacího políčka k podepsání manifestů aplikace a nasazení s pár veřejného a privátního klíče. Další informace o tom, jak to udělat najdete v tématu [postupy: přihlášení aplikace a manifesty nasazení](../../ide/how-to-sign-application-and-deployment-manifests.md).

 **Vyberte z úložiště** tlačítko

 Umožňuje zvolit existující certifikát z úložiště osobních certifikátů aktuálního uživatele. Můžete vybrat jednu z těchto certifikátů k podepsání manifestů vaší aplikace a nasazení.

 Kliknutím na tlačítko **zvolit z úložiště** otevře **vyberte certifikát, který** dialogové okno, které jsou uvedené certifikáty v úložišti osobních certifikátů, které jsou aktuálně platná (nevypršela) a které mají privátních klíčů. Účel certifikátu, který jste vybrali by měly obsahovat, podepisování kódu.

 Pokud kliknete na tlačítko **zobrazit vlastnosti certifikátu**, **podrobnosti certifikátu** zobrazí se dialogové okno. Toto dialogové okno obsahuje podrobné informace o certifikátu a obsahuje další možnosti. Můžete kliknout na **Další informace o certifikátech** chcete zobrazit další informace.

 **Vyberte ze souboru** tlačítko

 Umožňuje vybrat certifikát z existujícího souboru s klíčem.

 Kliknutím na tlačítko **vybrat ze souboru** otevře **vyberte soubor** dialogové okno, které vám umožní vybrat soubor certifikátu (.pfx) klíče. Soubor musí být chráněný heslem a již nemůže být umístěn v osobním úložišti certifikátů.

 V **zadejte heslo k otevření souboru** dialogovém okně zadejte heslo k otevřete soubor certifikátu (.pfx) klíče. Informace o hesle uložený v osobním úložišti certifikátů a seznamů vaše osobní kontejner klíčů.

 **Vytvoření testovacího certifikátu** tlačítko

 Umožňuje vytvořit certifikát pro testování. Testovací certifikát se používá k podepisování manifestů aplikace a nasazení vaší ClickOnce.

 Kliknutím na tlačítko **vytvořit testovací certifikát** otevře **vytvořit testovací certifikát** dialogové okno, ve kterém můžete zadat heslo pro soubor silného názvu klíče pro zkušební certifikát. Název souboru *projectname*_TemporaryKey.pfx. Pokud kliknete na tlačítko **OK** aniž by museli zadávat heslo, není soubor .pfx zašifrované heslo.

 **Adresa URL serveru časové razítko** pole

 Určuje adresu serveru, že časová razítka podpisu. Když zadáte certifikát, tento externí web ověřuje čas, který byl podepsán aplikace.

## <a name="assembly-signing"></a>Podepisování sestavení
 **Podepisování sestavení** zaškrtávací políčko

 Výběrem tohoto zaškrtávacího políčka k podepisování sestavení a vytvoření silně pojmenované soubor klíče. Další informace o podepisování sestavení pomocí **Návrhář projektu**, najdete v části [postupy: podepsání sestavení (Visual Studio)](../managing-assembly-and-manifest-signing.md#how-to-sign-an-assembly-in-visual-studio).

 Tato volba používá nástroj Al.exe poskytované [! ZAHRNOUT[winsdklong](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name).

 **Vyberte soubor klíče se silným názvem** seznamu

 Umožňuje zadat nový nebo existující silně pojmenované soubor klíče používaný k podepisování sestavení. Vyberte  **\<Procházet... >** vyberte existující soubor klíče.

 Vyberte  **\<nová... >** k vytvoření nového klíče souboru určený k podepisování sestavení. **Vytvořit klíč se silným názvem** se zobrazí dialogové okno, které můžete zadat název souboru klíče a chránit soubor klíče s heslem. Heslo musí mít alespoň 6 znaků. Pokud zadáte heslo, vytvoří se soubor Personal Information Exchange (.pfx); Pokud nezadáte heslo, vytvoří se soubor silně pojmenované klíče (.snk).

 **Změnit heslo** tlačítko

 Změní heslo pro soubor klíče Personal Information Exchange (.pfx), který se používá k podepsání sestavení.

 Kliknutím na tlačítko **změnit heslo** otevře **změnit heslo klíče** dialogové okno. V tomto dialogovém **staré heslo** je aktuální heslo pro soubor klíče. **Nové heslo** musí být alespoň 6 znaků. Informace o hesle je uložen v úložišti certifikátů aktuálního uživatele systému Windows.

 **Zpoždění podepsání** zaškrtávací políčko

 Zaškrtněte toto políčko, pokud chcete povolit podepisování zpoždění.

 Všimněte si, že zpoždění podepsané se nespustí a nemůžete ladit. Můžete však použít [Sn.exe (nástroj silným názvem)](/dotnet/framework/tools/sn-exe-strong-name-tool) s `-Vr` možnost pro přeskočení ověření během vývoje.

> [!NOTE]
> Když se přihlásíte sestavení, nemusí mít vždycky přístup k privátním klíčem. Organizace může mít například úzce chráněného pár klíčů, vývojáři nemají přístup k každý den. Veřejný klíč může být k dispozici, ale přístup k privátnímu klíči je omezen na několik z nich. V takovém případě můžete použít *odložené* nebo *částečné podepsání* zajistit veřejný klíč, dokud je předáno sestavení odložit přidání privátní klíč.


## <a name="see-also"></a>Viz také

- [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)
- [Správa sestavení a podepsání manifestu](../../ide/managing-assembly-and-manifest-signing.md)
- [Postupy: Podepsání manifestů aplikace a nasazení](../../ide/how-to-sign-application-and-deployment-manifests.md)
- [Postupy: podepsání sestavení (Visual Studio)](../managing-assembly-and-manifest-signing.md#how-to-sign-an-assembly-in-visual-studio)
- [Postupy: Podepsání sestavení silným názvem](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name)
- [Sestavení se silným názvem](/dotnet/framework/app-domains/strong-named-assemblies)