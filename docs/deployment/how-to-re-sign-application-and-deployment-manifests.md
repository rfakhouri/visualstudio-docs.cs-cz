---
title: 'Postupy: Opětovné podepisování manifestů aplikace a nasazení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Office applications, signing manifests
- deploying applications [ClickOnce], signing manifests
- deploying applications, signing manifests
- ClickOnce deployment, signing manifests
- Office development in Visual Studio, signing manifests
ms.assetid: d53bceb9-4d3b-4c22-b909-8f370e7231fb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba634ffb30d6459c940811f0ea080f8b71a37f34
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-re-sign-application-and-deployment-manifests"></a>Postupy: Opětovné podepisování manifestů aplikace a nasazení
Když provedete změny vlastnosti nasazení v manifest aplikace pro aplikace Windows Forms, aplikací Windows Presentation Foundation (xbap) nebo řešení pro systém Office, musíte znovu podepsat obě aplikace a manifesty nasazení s certifikát. Tento proces zajišťuje, že nejsou nainstalovány zmanipulovanou soubory do počítačů koncových uživatelů.  
  
 Jiné scénáře, kde byste měli znovu podepsat manifesty je, když chcete zákazníkům k podepsání aplikace a manifesty nasazení s svůj vlastní certifikát.  
  
## <a name="re-signing-the-application-and-deployment-manifests"></a>Aplikace a nasazení opětovné podepisování manifestů  
 Tento postup předpokládá, že jste již provedli změny souboru manifestu aplikace (manifest). Další informace najdete v tématu [postupy: Změna vlastností nasazení](http://msdn.microsoft.com/en-us/66052a3a-8127-4964-8147-2477ef5d1472).  
  
#### <a name="to-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Chcete-li znovu podepsat aplikace a nasazení manifesty s Mage.exe  
  
1.  Otevřete **Visual Studio – příkazový řádek** okno.  
  
2.  Změňte adresář na složku, která obsahuje manifestu soubory, které se chcete přihlásit.  
  
3.  Zadejte následující příkaz k podepsání souboru manifestu aplikace. Nahraďte název souboru manifestu plus rozšíření manifestu. Nahraďte certifikát úplnou nebo relativní cestu k souboru certifikátu a nahraďte heslo pro tento certifikát heslo.  
  
    ```  
    mage -sign ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     Můžete například spustit následující příkaz k podepsání manifestu aplikace pro doplněk, formuláře Windows aplikace nebo aplikace prohlížeče Windows Presentation Foundation. Dočasné certifikáty, které jsou vytvořené pomocí sady Visual Studio není vhodné pro nasazení do produkčního prostředí.  
  
    ```  
    mage -sign WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -sign ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -sign WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
4.  Zadejte následující příkaz k aktualizaci a podepsání souboru manifestu nasazení, nahraďte zástupné názvy jako v předchozím kroku.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     Můžete například spustit následující příkaz k aktualizaci a podepsání manifestu nasazení pro doplněk aplikace Excel, aplikace Windows Forms nebo aplikace prohlížeče Windows Presentation Foundation.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  Volitelně můžete zkopírovat hlavní manifest nasazení (publikování\\*appname*.application) do vašeho adresáře nasazení verze (publish\Application soubory\\*appname*_ *verze*).  
  
## <a name="updating-and-re-signing-the-application-and-deployment-manifests"></a>Aktualizace a opětovné podepisování manifestů nasazení aplikace a  
 Tento postup předpokládá, že již provedené změny do vaší aplikace, manifest souboru (manifest), ale, že existují další soubory, které byly aktualizovány. Když jsou aktualizovány soubory musí také aktualizovat hodnotu hash, který představuje soubor.  
  
#### <a name="to-update-and-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Pokud chcete aktualizovat a znovu podepsat aplikace a nasazení manifesty s Mage.exe  
  
1.  Otevřete **Visual Studio – příkazový řádek** okno.  
  
2.  Změňte adresář na složku, která obsahuje manifestu soubory, které se chcete přihlásit.  
  
3.  Odeberte příponu souboru .deploy z soubory v zadané výstupní složce publikování.  
  
4.  Zadejte následující příkaz k aktualizaci manifest aplikace s novými hodnotami hash pro aktualizované soubory a podepsání souboru manifestu aplikace. Nahraďte název souboru manifestu plus rozšíření manifestu. Nahraďte certifikát úplnou nebo relativní cestu k souboru certifikátu a nahraďte heslo pro tento certifikát heslo.  
  
    ```  
    mage -update ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     Můžete například spustit následující příkaz k podepsání manifestu aplikace pro doplněk, formuláře Windows aplikace nebo aplikace prohlížeče Windows Presentation Foundation. Dočasné certifikáty, které jsou vytvořené pomocí sady Visual Studio není vhodné pro nasazení do produkčního prostředí.  
  
    ```  
    mage -update WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  Zadejte následující příkaz k aktualizaci a podepsání souboru manifestu nasazení, nahraďte zástupné názvy jako v předchozím kroku.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     Můžete například spustit následující příkaz k aktualizaci a podepsání manifestu nasazení pro doplněk aplikace Excel, aplikace Windows Forms nebo aplikace prohlížeče Windows Presentation Foundation.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
6.  Přidáte příponu souboru .deploy zpět k souborům, s výjimkou souborů manifestů aplikace a nasazení.  
  
7.  Volitelně můžete zkopírovat hlavní manifest nasazení (publikování\\*appname*.application) do vašeho adresáře nasazení verze (publish\Application soubory\\*appname*_ *verze*).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce a kód Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md)   
 [Postupy: povolení nastavení zabezpečení ClickOnce](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Postupy: nastavení zóny zabezpečení pro aplikace ClickOnce](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Postupy: ladění aplikace ClickOnce s omezenými oprávněními](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Postupy: Přidání důvěryhodného vydavatele ke klientskému počítači pro aplikace ClickOnce](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [Postupy: Konfigurace chování výzvy důvěryhodnosti ClickOnce](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)