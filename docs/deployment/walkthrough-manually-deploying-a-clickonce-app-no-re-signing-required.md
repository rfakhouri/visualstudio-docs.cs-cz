---
title: 'Návod: Ruční nasazení aplikace ClickOnce, který nevyžaduje službu nevyžaduje opětovné podepsání a které zachovává informace o konfiguraci | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- branding
- preserved branding information
- ClickOnce deployment, manually
- multiple ClickOnce deployment and branding
- ClickOnce deployment, SDK tools
- customer deployments
- manual ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, deployed by others
ms.assetid: c21822fb-d4ee-42e4-b72d-41ee9786efe5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0584aac376345bc508e5f2088decd45b8c64783b
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information"></a>Návod: Ruční nasazení aplikace ClickOnce, jež nevyžaduje opětovné podepsání a které zachovává údaje o poskytovateli
Při vytváření [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace a pak umožnit zákazníkovi k publikování a nasazení, zákazník tradičně museli aktualizovat manifest nasazení a podepište ho znovu. Přesto, že je stále upřednostňovanou metodou ve většině případů, rozhraní .NET Framework 3.5 umožňuje vytvářet [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, které lze nasadit zákazníky bez nutnosti znovu vygenerovat nový manifest nasazení. Další informace najdete v tématu [nasazení ClickOnce aplikace pro testování a produkční servery bez Resigning](../deployment/deploying-clickonce-applications-for-testing-and-production-without-resigning.md).  
  
 Při vytváření [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace a pak ji předáte zákazníkovi k publikování a nasazení, aplikace můžete použít přidání údajů zákazníka nebo můžete zachovat vaše obchodní údaje. Například pokud aplikace je jednou speciální aplikací, můžete chtít zachovat vaše obchodní údaje. Pokud aplikace vysoce přizpůsobený pro každého zákazníka, můžete chtít použít přidání údajů zákazníka. Když dáváte aplikaci organizaci nasadit, povolí rozhraní .NET Framework 3.5 můžete zachovat vaše obchodní údaje, informace o vydavateli a podpis zabezpečení. Další informace najdete v tématu [vytváření aplikací ClickOnce pro ostatní k nasazení](../deployment/creating-clickonce-applications-for-others-to-deploy.md).  
  
> [!NOTE]
>  V tomto návodu vytvoříte nasazení ručně pomocí nástroje příkazového řádku Mage.exe nebo grafický nástroj MageUI.exe. Další informace o ruční nasazení najdete v tématu [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K provedení kroků v tomto návodu budete potřebovat následující:  
  
-   Aplikace Windows Forms, který budete chtít nasadit. Tato aplikace bude označovány jako WindowsFormsApp1.  
  
-   Visual Studio nebo sady Windows SDK.  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageexe"></a>K nasazení aplikace ClickOnce s více nasazení a brandingu podporu pomocí Mage.exe  
  
1.  Otevřete příkazový řádek sady Visual Studio nebo [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] příkazový řádek a přejděte do adresáře, ve které budete ukládat vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] soubory.  
  
2.  Vytvořte adresář s názvem po aktuální verzi vašeho nasazení. Pokud je při prvním nasazení aplikace, pravděpodobně zvolíte **1.0.0.0**.  
  
    > [!NOTE]
    >  Verzi vašeho nasazení může být odlišná od verze soubory aplikace.  
  
3.  Vytvořit podadresář s názvem **bin** a zkopírujte všechny soubory aplikace v tomto poli, včetně spustitelné soubory, sestavení, prostředky a datových souborů.  
  
4.  Vygenerujte manifest aplikace pomocí volání Mage.exe.  
  
    ```  
    mage -New Application -ToFile 1.0.0.0\WindowsFormsApp1.exe.manifest -Name "Windows Forms App 1" -Version 1.0.0.0 -FromDirectory 1.0.0.0\bin -UseManifestForTrust true -Publisher "A. Datum Corporation"  
    ```  
  
5.  Podepsání manifestu aplikace s digitální certifikát.  
  
    ```  
    mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx  
    ```  
  
6.  Generování manifestu nasazení s volání Mage.exe. Ve výchozím nastavení, Mage.exe označíte vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení jako instalované aplikace, takže to můžete spustit online a offline. Chcete-li aplikace k dispozici jenom v případě, že uživatel je online, použijte `-i` argument s hodnotou `f`. Vzhledem k tomu, že tato aplikace bude využívat více funkcí nasazení, vyloučit `-providerUrl` argument Mage.exe. (Ve verzích rozhraní .NET Framework verze 3.5, s výjimkou `-providerUrl` pro offline aplikace bude mít za následek chybu.)  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "Windows Forms App 1" -Version 1.0.0.0 -AppManifest 1.0.0.0\WindowsFormsApp1.manifest   
    ```  
  
7.  Neregistrujte manifest nasazení.  
  
8.  Zadejte všechny soubory zákazníkovi, který nasadí aplikaci ve své síti.  
  
9. Zákazník musí v tomto okamžiku podepsání manifestu nasazení s vlastním certifikát vygenerovaný sám sebou. Například pokud zákazník funguje pro společnost s názvem společnosti Adventure Works, může generovat certifikát podepsaný svým držitelem pomocí nástroje MakeCert.exe. Pak pomocí nástroje Pvk2pfx.exe souborů vytvořených pomocí MakeCert.exe do souboru PFX, který se dá předat do Mage.exe.  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
10. Zákazník dále používá tento certifikát pro podepsání manifestu nasazení.  
  
    ```  
    mage -Sign WindowsFormsApp1.application -CertFile MyCert.pfx  
    ```  
  
11. Zákazník nasadí aplikaci uživatelům.  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageuiexe"></a>K nasazení aplikace ClickOnce s více nasazení a brandingu podporu pomocí MageUI.exe  
  
1.  Otevřete příkazový řádek sady Visual Studio nebo [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] příkazový řádek a přejděte do adresáře, ve které budete ukládat vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] soubory.  
  
2.  Vytvořit podadresář s názvem **bin** a zkopírujte všechny soubory aplikace v tomto poli, včetně spustitelné soubory, sestavení, prostředky a datových souborů.  
  
3.  Vytvořte podadresář s názvem aktuální verzi vašeho nasazení. Pokud je při prvním nasazení aplikace, pravděpodobně zvolíte **1.0.0.0**.  
  
    > [!NOTE]
    >  Verzi vašeho nasazení může být odlišná od verze soubory aplikace.  
  
4.  Přesunout \\ **bin** adresář do adresáře, který jste vytvořili v kroku 2.  
  
5.  Spusťte grafický nástroj MageUI.exe.  
  
    ```  
    MageUI.exe  
    ```  
  
6.  Vytvořit nové manifest aplikace výběrem **soubor**, **nový**, **Application Manifest** z nabídky.  
  
7.  Na výchozí **název** , zadejte název a verze počet toto nasazení. Zadejte také hodnotu **vydavatele**, který se použije jako název složky pro aplikace zástupce odkaz v nabídce Start při nasazení.  
  
8.  Vyberte **možnosti aplikace** a klikněte na **použít Manifest aplikace pro informace o vztahu důvěryhodnosti**. Tato akce povolí třetích stran branding pro tento [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
9. Vyberte **soubory** a klikněte **Procházet** tlačítko vedle textového pole adresář aplikace.  
  
10. Vyberte adresář, který obsahuje soubory aplikace, které jste vytvořili v kroku 2 a klikněte na tlačítko **OK** v dialogovém okně Výběr složky.  
  
11. Klikněte **vyplnit** tlačítko Přidat do seznamu souborů pro všechny soubory aplikace. Pokud vaše aplikace obsahuje více než jeden spustitelný soubor, označte hlavní spustitelný soubor pro toto nasazení jako spouštěcí aplikaci tak, že vyberete **vstupní bod** z **typ souboru** rozevíracího seznamu. (Pokud vaše aplikace obsahuje pouze jeden spustitelný soubor, MageUI.exe ho označí za vás.)  
  
12. Vyberte **oprávněních** a vyberte úroveň důvěryhodnosti, které potřebujete k vyhodnocení aplikace. Výchozí hodnota je **úplný vztah důvěryhodnosti**, která budou vhodná pro většinu aplikací.  
  
13. Vyberte **soubor**, **Uložit** z nabídky a uložte manifest aplikace. Zobrazí se výzva k podepsání manifestu aplikace, když jste jej uložili.  
  
14. Pokud máte certifikát uložený jako soubor ve vašem systému souborů, použijte **podepsat jako soubor certifikátu** možnost a vyberte certifikát ze systému souborů pomocí se třemi tečkami (**...** ) tlačítko.  
  
     -nebo-  
  
     Pokud váš certifikát je uložen v úložišti certifikátů, které jsou přístupné z počítače, vyberte **podepsat s uložený certifikát**a vyberte certifikát z poskytnutého seznamu.  
  
15. Vyberte **soubor**, **nový**, **Manifest nasazení** z nabídky pro vytvoření manifestu nasazení a potom na **název** kartě, zadejte název a číslo verze (**1.0.0.0** v tomto příkladu).  
  
16. Přepnout **aktualizace** a zadejte, jak často se má aktualizovat v této aplikaci. Pokud vaše aplikace používá [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] rozhraní API nasazení ke kontrole aktualizací samostatně, zrušte zaškrtnutí políčka s názvem bez přípony **této aplikace by měla vyhledat aktualizace**.  
  
17. Přepnout **odkaz aplikace** kartě. Všechny hodnoty na této kartě můžete předem zadat kliknutím **vyberte Manifest** tlačítko a výběrem manifest aplikace jste vytvořili v předchozích krocích.  
  
18. Zvolte **Uložit** a uložte manifest nasazení na disk. Zobrazí se výzva k podepsání manifestu aplikace, když jste jej uložili. Klikněte na tlačítko **zrušit** pro uložení manifestu bez podepisování.  
  
19. Zadejte všechny soubory, aplikace k odběrateli.  
  
20. Zákazník musí v tomto okamžiku podepsání manifestu nasazení s vlastním certifikát vygenerovaný sám sebou. Například pokud zákazník funguje pro společnost s názvem společnosti Adventure Works, může generovat certifikát podepsaný svým držitelem pomocí nástroje MakeCert.exe. Pak pomocí nástroje Pvk2pfx.exe souborů vytvořených pomocí MakeCert.exe do souboru PFX, který se dá předat do MageUI.exe.  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
21. S certifikátem, vygeneruje zákazník nyní podepíše manifest nasazení otevřením manifest nasazení v MageUI.exe, a potom ho uložit. Když se zobrazí dialogové okno podpisový, zákazník vybírá **podepsat jako soubor certifikátu** možnost a vybere soubor PFX uložil na disku.  
  
22. Zákazník nasadí aplikaci uživatelům.  
  
## <a name="next-steps"></a>Další kroky  
  
## <a name="see-also"></a>Viz také  
 [Mage.exe (generování manifestu a nástroj pro úpravy)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (generování manifestu a nástroj pro úpravy, grafický klient)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [MakeCert](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx)