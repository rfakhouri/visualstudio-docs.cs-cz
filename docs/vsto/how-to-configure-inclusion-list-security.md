---
title: "Postupy: konfigurace zabezpečení se seznamem povolených | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio
- inclusion lists [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0b95b85f028ac003cedb05248b6884c24ca32008
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-configure-inclusion-list-security"></a>Postupy: Konfigurace zabezpečení se seznamem povolených položek
  Pokud máte oprávnění správce, můžete nakonfigurovat [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěryhodný dotaz na ovládací prvek zda koncoví uživatelé mají možnost instalace řešení pro systém Office uložením rozhodnutí o vztahu důvěryhodnosti na seznam povolených položek. Informace o seznamech povolených položek najdete v tématu [důvěřující řešení pro systém Office pomocí pomocí seznamy povolených položek](../vsto/trusting-office-solutions-by-using-inclusion-lists.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Pro řešení, které jsou v každé z pěti zóny můžete nastavit následující možnosti:  
  
-   Povolit [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěřovat výzva klíč a seznam povolených položek. Můžete povolit koncovým uživatelům udělit vztah důvěryhodnosti řešení pro systém Office, které jsou podepsané s žádný certifikát.  
  
-   Omezit [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěřovat výzva klíč a seznam povolených položek. Můžete povolit koncovým uživatelům pro instalaci řešení pro systém Office, které jsou podepsané certifikátem, který identifikuje vydavatele, ale který již není důvěryhodný.  
  
-   Zakažte [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěřovat výzva klíč a seznam povolených položek. Koncoví uživatelé dokáže zabránit instalaci jakéhokoli řešení Office, které není podepsáno s explicitně důvěryhodný certifikát.  
  
## <a name="enabling-the-inclusion-list"></a>Povolení seznam povolených položek  
 Povolte seznam povolených položek pro zónu, když chcete koncovým uživatelům bude nabídnuta možnost instalace a spuštění řešení Office, která pochází z této zóny.  
  
#### <a name="to-enable-the-inclusion-list-by-using-the-registry-editor"></a>Chcete-li povolit seznam povolených položek pomocí Editoru registru  
  
1.  Otevřete editor registru:  
  
    1.  Klikněte na tlačítko **spustit**a potom klikněte na **spustit**.  
  
    2.  V **otevřete** zadejte **regedt32.exe**a potom klikněte na **OK**.  
  
2.  Najděte následující klíč registru:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Pokud klíč neexistuje, vytvořte ho.  
  
3.  Přidejte následující podklíče jako **řetězcovou hodnotu**, pokud ještě neexistují, s přiřazenými hodnotami.  
  
    |Hodnota řetězce podklíče|Hodnota|  
    |-------------------------|-----------|  
    |**Internet**|**AuthenticodeRequired**|  
    |**UntrustedSites**|**Zakázané**|  
    |**Tento počítač**|**Povoleno**|  
    |**LocalIntranet**|**Povoleno**|  
    |**TrustedSites**|**Povoleno**|  
  
     Ve výchozím nastavení **Internet** má hodnotu **AuthenticodeRequired** a **UntrustedSites** má hodnotu **zakázané**.  
  
#### <a name="to-enable-the-inclusion-list-programmatically"></a>Chcete-li povolit seznam povolených položek prostřednictvím kódu programu  
  
1.  Vytvořte konzolovou aplikaci Visual Basic a Visual C#.  
  
2.  Otevřete soubor Program.vb nebo Program.cs soubor pro úpravy a přidejte následující kód.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Enabled")  
    key.SetValue("LocalIntranet", "Enabled")  
    key.SetValue("Internet", "AuthenticodeRequired")  
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
  
## <a name="restricting-the-inclusion-list"></a>Omezení seznam povolených položek  
 Seznam povolených položek omezte tak, aby řešení musí být podepsané Authenticode certifikáty, které známé identity, než se uživateli zobrazí výzva pro rozhodnutí o vztahu důvěryhodnosti.  
  
#### <a name="to-restrict-the-inclusion-list"></a>Omezte seznam povolených položek  
  
1.  Otevřete editor registru:  
  
    1.  Klikněte na tlačítko **spustit**a potom klikněte na **spustit**.  
  
    2.  V **otevřete** zadejte **regedt32.exe**a potom klikněte na **OK**.  
  
2.  Najděte následující klíč registru:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Pokud klíč neexistuje, vytvořte ho.  
  
3.  Přidejte následující podklíče jako **řetězcovou hodnotu**, pokud ještě neexistují, s přiřazenými hodnotami.  
  
    |Hodnota řetězce podklíče|Hodnota|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**Zakázané**|  
    |**Internet**|**AuthenticodeRequired**|  
    |**Tento počítač**|**AuthenticodeRequired**|  
    |**LocalIntranet**|**AuthenticodeRequired**|  
    |**TrustedSites**|**AuthenticodeRequired**|  
  
     Ve výchozím nastavení **Internet** má hodnotu **AuthenticodeRequired** a **UntrustedSites** má hodnotu **zakázané**.  
  
#### <a name="to-restrict-the-inclusion-list-programmatically"></a>Omezte seznam povolených položek prostřednictvím kódu programu  
  
1.  Vytvořte konzolovou aplikaci Visual Basic a Visual C#.  
  
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
  
## <a name="disabling-the-inclusion-list"></a>Zakázání seznam povolených položek  
 Seznam povolených položek můžete zakázat tak, aby koncoví uživatelé můžou instalovat jenom řešení, které jsou podepsané důvěryhodným a známým certifikátem.  
  
#### <a name="to-disable-the-inclusion-list"></a>Chcete-li zakázat seznam povolených položek  
  
1.  Otevřete editor registru:  
  
    1.  Klikněte na tlačítko **spustit**a potom klikněte na **spustit**.  
  
    2.  V **otevřete** zadejte **regedt32.exe**a potom klikněte na **OK**.  
  
2.  Pokud to již neexistuje, vytvořte následující klíč registru:  
  
     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel**  
  
3.  Přidejte následující podklíče jako **řetězcovou hodnotu**, pokud ještě neexistují, s přiřazenými hodnotami.  
  
    |Hodnota řetězce podklíče|Hodnota|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**Zakázané**|  
    |**Internet**|**Zakázané**|  
    |**Tento počítač**|**Zakázané**|  
    |**LocalIntranet**|**Zakázané**|  
    |**TrustedSites**|**Zakázané**|  
  
#### <a name="to-disable-the-inclusion-list-programmatically"></a>Chcete-li zakázat seznam povolených položek prostřednictvím kódu programu  
  
1.  Vytvořte konzolovou aplikaci Visual Basic a Visual C#.  
  
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
 [Důvěřující řešení Office s použitím seznamech povolených položek](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
  
  