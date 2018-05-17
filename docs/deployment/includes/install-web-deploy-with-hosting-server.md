Nasazení webu 3.6 pro hostování servery poskytuje další konfiguraci funkce, které umožňují vytvářet soubor nastavení publikování v uživatelském rozhraní.

1. Pokud máte nasazení 3.6 Web, který je již nainstalována v systému Windows Server, odinstalujte ji pomocí **ovládací panely** > **programy** > **odinstalační Program**.

2. Dále nainstalujte 3.6 nasadit Web pro hostování servery v systému Windows Server.

    Instalovat nasazení webu pro hostování servery, použijte [instalačního programu webové platformy (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx). (Odkaz Web Platform Installer ze služby IIS, vyberete **IIS** v levém podokně Správce serveru. Pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.)

    V instalačním programu webové platformy můžete najít **nasazení webu pro hostování servery** na kartě aplikace.

3. V systému Windows Server, přejděte na **vybrat role serveru** > **webového serveru (IIS)** > **nástroje pro správu**a pak vyberte **služby IIS Skripty a nástroje správy** role, klikněte na tlačítko **Další**a poté nainstalujte roli.

    ![Instalace nástrojů a skriptů pro správu služby IIS.](../../deployment/media/tutorial-iis-management-scripts-and-tools.png)

    Tato role je potřeba povolit generování soubor nastavení publikování.

4. Ověřte, zda Web Deploy je spuštěna správně otevřením **ovládací panely > systém a zabezpečení > Nástroje pro správu > služby** a ujistěte se, že **Služba agenta pro nasazení webu** běží (na název služby se liší v starší verze).

    Pokud není spuštěna Služba agenta, spusťte ji. Pokud není přítomen vůbec, přejděte na **ovládací panely > programy > odinstalovat program**, Najít **Microsoft Web Deploy <version>** . Zvolit **změnu** instalaci a ujistěte se, že zvolíte **bude nainstalována na místní pevný disk** pro součásti nástroje nasazení webu. Proveďte kroky instalace změnu.