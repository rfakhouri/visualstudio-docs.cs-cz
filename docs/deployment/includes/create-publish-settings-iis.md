
1. Zavřete a znovu otevřete konzolu pro správu služby IIS zobrazíte možnosti aktualizované konfigurace v uživatelském rozhraní.

1. Ve službě IIS, klikněte pravým tlačítkem myši **Default Web Site**, zvolte **nasadit** > **konfigurace nasazení publikování na webu**.

    ![Nakonfigurujte konfiguraci nasazení webu](../../deployment/media/tutorial-configure-web-deploy-publishing.png)

1. V **konfigurace nasazení publikování na webu** dialogové okno pole, zkontrolujte nastavení.

1. Klikněte na tlačítko **instalační program**.

    V **výsledky** panelu ukazuje výstup, které přístupová práva jsou udělena zadaného uživatele a že soubor s *.publishsettings* přípona souboru byla vygenerována v uvedeném v dialogovém okně umístění pole.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <publishData>
      <publishProfile
        publishUrl="https://myhostname:8172/msdeploy.axd"
        msdeploySite="Default Web Site"
        destinationAppUrl="http://myhostname:80/"
        mySQLDBConnectionString=""
        SQLServerDBConnectionString=""
        profileName="Default Settings"
        publishMethod="MSDeploy"
        userName="myhostname\myusername" />
    </publishData>
    ```

    V závislosti na konfiguraci systému Windows Server a služby IIS najdete v části různé hodnoty v souboru XML. Zde jsou několik podrobnosti o hodnoty, které se zobrazí:

    * *Msdeploy.axd* souboru v odkazuje `publishUrl` atribut je dynamicky generovaném soubor obslužné rutiny HTTP pro nasazení webu. (Pro účely testování `http://myhostname:8172` obecně funguje stejně.)
    * `publishUrl` Port nastaven na port 8172, což je výchozí nastavení pro nasazení webu.
    * `destinationAppUrl` Port je nastavený na portu 80, což výchozí nastavení pro službu IIS.
    * Pokud není možné se připojit ke vzdálenému hostiteli v sadě Visual Studio pomocí názvu hostitele (v následujících krocích), otestujte IP adresu místo názvu hostitele.

    > [!NOTE]
    > Pokud publikujete IIS a běžící na virtuálním počítači Azure, musíte otevřít Web Deploy a porty služby IIS ve skupině zabezpečení sítě. Podrobné informace najdete v tématu [instalace a spuštění služby IIS](/azure/virtual-machines/windows/quick-create-portal#open-port-80-for-web-traffic).

1. Zkopírujte tento soubor do počítače, kde je spuštěn nástroj Visual Studio.
