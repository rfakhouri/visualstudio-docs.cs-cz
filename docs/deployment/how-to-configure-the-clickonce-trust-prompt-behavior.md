---
title: 'Postupy: Konfigurace chování výzvy důvěryhodnosti ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, install without prompting
- deploying applications [ClickOnce], trust prompt
- ClickOnce applications, install without prompting
- ClickOnce applications, trust prompt
- ClickOnce deployment, trust prompt
ms.assetid: cc04fa75-012b-47c9-9347-f4216be23cf2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d37e5fa465a5e19b1bfb7577f6ab06c61782f775
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-configure-the-clickonce-trust-prompt-behavior"></a>Postupy: Konfigurace chování výzvy důvěryhodnosti ClickOnce
Můžete nakonfigurovat vztahu důvěryhodnosti ClickOnce řídit, jestli koncoví uživatelé mají možnost instalace aplikace ClickOnce, například aplikace Windows Forms, aplikace Windows Presentation Foundation, konzolové aplikace, prohlížeč WPF aplikace a řešení pro systém Office. Nakonfigurujete výzvu vztahu důvěryhodnosti nastavením klíče registru na počítači koncového uživatele.  
  
 V následující tabulce jsou uvedeny možnosti konfigurace, které lze použít pro každý z pěti zóny (Internet, UntrustedSites, tento počítač, LocalIntranet a TrustedSites).  
  
|Možnost|Hodnota nastavení registru|Popis|  
|------------|----------------------------|-----------------|  
|Povolte výzvu vztahu důvěryhodnosti.|`Enabled`|Vztahu důvěryhodnosti ClickOnce je zobrazení tak, aby koncoví uživatelé můžete udělit vztah důvěryhodnosti pro aplikace ClickOnce.|  
|Omezte výzvu vztahu důvěryhodnosti.|`AuthenticodeRequired`|Vztahu důvěryhodnosti ClickOnce se zobrazí jenom v případě ClickOnce aplikace jsou podepsané certifikátem, který identifikuje vydavatele.|  
|Zakážete výzvu vztahu důvěryhodnosti.|`Disabled`|Vztahu důvěryhodnosti ClickOnce se nezobrazuje u všech aplikací ClickOnce, které nejsou podepsané certifikátem explicitně důvěryhodný.|  
  
 Následující tabulka uvádí výchozí chování pro každou zónu. Sloupec aplikace odpovídá formulářových aplikací Windows, aplikace Windows Presentation Foundation, Prohlížečových aplikací a konzolové aplikace.  
  
|zóny|Aplikace|řešení Office|  
|----------|------------------|----------------------|  
|`MyComputer`|`Enabled`|`Enabled`|  
|`LocalIntranet`|`Enabled`|`Enabled`|  
|`TrustedSites`|`Enabled`|`Enabled`|  
|`Internet`|`Enabled`|`AuthenticodeRequired`|  
|`UntrustedSites`|`Disabled`|`Disabled`|  
  
 Toto nastavení můžete přepsat povolením, omezení nebo zakázáním vztahu důvěryhodnosti ClickOnce.  
  
## <a name="enabling-the-clickonce-trust-prompt"></a>Povolení vztahu důvěryhodnosti ClickOnce  
 Povolte výzvu vztahu důvěryhodnosti pro zónu, když chcete koncovým uživatelům bude nabídnuta možnost instalace a spuštění jakékoli aplikace ClickOnce, která pochází z této zóny.  
  
#### <a name="to-enable-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>Povolení vztahu důvěryhodnosti ClickOnce pomocí Editoru registru  
  
1.  Otevřete editor registru:  
  
    1.  Klikněte na tlačítko **spustit**a potom klikněte na **spustit**.  
  
    2.  V **otevřete** zadejte `regedit32`a potom klikněte na **OK**.  
  
2.  Najděte následující klíč registru:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Pokud klíč neexistuje, vytvořte ho.  
  
3.  Přidejte následující podklíče jako **řetězcovou hodnotu**, pokud ještě neexistují, s přiřazenými hodnotami, které jsou uvedené v následující tabulce.  
  
    |Hodnota řetězce podklíče|Hodnota|  
    |-------------------------|-----------|  
    |`Internet`|`Enabled`|  
    |`UntrustedSites`|`Disabled`|  
    |`MyComputer`|`Enabled`|  
    |`LocalIntranet`|`Enabled`|  
    |`TrustedSites`|`Enabled`|  
  
     Pro řešení Office `Internet` nemá výchozí hodnotu `AuthenticodeRequired` a `UntrustedSites` má hodnotu `Disabled`. Pro všechny ostatní `Internet` nemá výchozí hodnotu `Enabled`.  
  
#### <a name="to-enable-the-clickonce-trust-prompt-programmatically"></a>Chcete-li povolit vztahu důvěryhodnosti ClickOnce prostřednictvím kódu programu  
  
1.  Vytvořte konzolovou aplikaci Visual Basic a Visual C# v sadě Visual Studio.  
  
2.  Otevřete soubor Program.vb nebo Program.cs soubor pro úpravy a přidejte následující kód.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Enabled")  
    key.SetValue("LocalIntranet", "Enabled")  
    key.SetValue("Internet", "Enabled")  
    key.SetValue("TrustedSites", "Enabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Enabled");  
    key.SetValue("LocalIntranet", "Enabled");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "Enabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Sestavte a spusťte aplikaci.  
  
## <a name="restricting-the-clickonce-trust-prompt"></a>Omezení vztahu důvěryhodnosti ClickOnce  
 Omezte výzvu vztahu důvěryhodnosti, aby řešení musí být podepsané Authenticode certifikáty, které známé identity, než se uživateli zobrazí výzva pro rozhodnutí o vztahu důvěryhodnosti.  
  
#### <a name="to-restrict-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>Omezení vztahu důvěryhodnosti ClickOnce pomocí Editoru registru  
  
1.  Otevřete editor registru:  
  
    1.  Klikněte na tlačítko **spustit**a potom klikněte na **spustit**.  
  
    2.  V **otevřete** zadejte `regedit`a potom klikněte na **OK**.  
  
2.  Najděte následující klíč registru:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Pokud klíč neexistuje, vytvořte ho.  
  
3.  Přidejte následující podklíče jako **řetězcovou hodnotu**, pokud ještě neexistují, s přiřazenými hodnotami, které jsou uvedené v následující tabulce.  
  
    |Hodnota řetězce podklíče|Hodnota|  
    |-------------------------|-----------|  
    |`UntrustedSites`|`Disabled`|  
    |`Internet`|`AuthenticodeRequired`|  
    |`MyComputer`|`AuthenticodeRequired`|  
    |`LocalIntranet`|`AuthenticodeRequired`|  
    |`TrustedSites`|`AuthenticodeRequired`|  
  
#### <a name="to-restrict-the-clickonce-trust-prompt-programmatically"></a>Chcete-li omezit vztahu důvěryhodnosti ClickOnce prostřednictvím kódu programu  
  
1.  Vytvořte konzolovou aplikaci Visual Basic a Visual C# v sadě Visual Studio.  
  
2.  Otevřete soubor Program.vb nebo Program.cs soubor pro úpravy a přidejte následující kód.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "AuthenticodeRequired")  
    key.SetValue("LocalIntranet", "AuthenticodeRequired")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "AuthenticodeRequired")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "AuthenticodeRequired");  
    key.SetValue("LocalIntranet", "AuthenticodeRequired");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "AuthenticodeRequired");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Sestavte a spusťte aplikaci.  
  
## <a name="disabling-the-clickonce-trust-prompt"></a>Zakázání vztahu důvěryhodnosti ClickOnce  
 Výzvu vztahu důvěryhodnosti můžete zakázat tak, aby koncoví uživatelé nejsou zadána možnost instalace řešení, které ještě nejsou důvěryhodné v jejich zásady zabezpečení.  
  
#### <a name="to-disable-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>Zakázání vztahu důvěryhodnosti ClickOnce pomocí Editoru registru  
  
1.  Otevřete editor registru:  
  
    1.  Klikněte na tlačítko **spustit**a potom klikněte na **spustit**.  
  
    2.  V **otevřete** zadejte `regedit`a potom klikněte na **OK**.  
  
2.  Najděte následující klíč registru:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Pokud klíč neexistuje, vytvořte ho.  
  
3.  Přidejte následující podklíče jako **řetězcovou hodnotu**, pokud ještě neexistují, s přiřazenými hodnotami, které jsou uvedené v následující tabulce.  
  
    |Hodnota řetězce podklíče|Hodnota|  
    |-------------------------|-----------|  
    |`UntrustedSites`|`Disabled`|  
    |`Internet`|`Disabled`|  
    |`MyComputer`|`Disabled`|  
    |`LocalIntranet`|`Disabled`|  
    |`TrustedSites`|`Disabled`|  
  
#### <a name="to-disable-the-clickonce-trust-prompt-programmatically"></a>Chcete-li zakázat vztahu důvěryhodnosti ClickOnce prostřednictvím kódu programu  
  
1.  Vytvořte konzolovou aplikaci Visual Basic a Visual C# v sadě Visual Studio.  
  
2.  Otevřete soubor Program.vb nebo Program.cs soubor pro úpravy a přidejte následující kód.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Disabled")  
    key.SetValue("LocalIntranet", "Disabled")  
    key.SetValue("Internet", "Disabled")  
    key.SetValue("TrustedSites", "Disabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Disabled");  
    key.SetValue("LocalIntranet", "Disabled");  
    key.SetValue("Internet", "Disabled");  
    key.SetValue("TrustedSites", "Disabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
  
    ```  
  
3.  Sestavte a spusťte aplikaci.  
  
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
 [Postupy: Opětovné podepisování manifestů aplikace a nasazení](../deployment/how-to-re-sign-application-and-deployment-manifests.md)