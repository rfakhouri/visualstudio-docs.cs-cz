---
title: Vzdálené pracovní prostory pro R
description: Jak nastavit vzdálené pracovní prostory R a připojte se k němu ze sady Visual Studio.
ms.date: 12/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 84a9c2bddb74402711217427b3471713562cce0a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="setting-up-remote-workspaces"></a>Nastavení vzdálené pracovní prostory

Tento článek vysvětluje postup konfigurace vzdáleného serveru pomocí protokolu SSL a příslušné službě R. To umožňuje R nástrojů pro Visual Studio (RTVS) pro připojení k vzdálené prostoru na tomto serveru.

- [Požadavky na vzdáleném počítači](#remote-computer-requirements)
- [Nainstalujte certifikát SSL](#install-an-ssl-certificate)
- [Nainstalujte certifikát SSL v systému Windows](#install-an-ssl-certificate-on-windows)
- [Na Ubuntu nainstalovat certifikát SSL](#install-an-ssl-certificate-on-ubuntu)
- [Nainstalujte R služby v systému Windows](#install-r-services-on-windows)
- [Nainstalujte R služby v systému Linux](#install-r-services-on-Linux)
- [Konfigurace služby R](#configure-r-services)
- [Odstraňování potíží](#troubleshooting)

## <a name="remote-computer-requirements"></a>Požadavky na vzdáleném počítači

- Windows 10, Windows Server 2016 nebo Windows Server 2012 R2. RTVS taky vyžaduje.
- [Rozhraní .NET framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981) nebo vyšší

## <a name="install-an-ssl-certificate"></a>Nainstalujte certifikát SSL

RTVS vyžaduje, aby se stane veškerá komunikace se vzdáleným serverem prostřednictvím protokolu HTTP, který vyžaduje certifikát SSL na serveru. Můžete použít certifikát podepsaný důvěryhodnou certifikační autoritou (doporučeno) nebo certifikát podepsaný svým držitelem. (Certifikát podepsaný svým držitelem vede RTVS pro upozornění na problém při připojení). Pomocí některé z nich musíte pak jej nainstalovat na počítač a povolení přístupu k jeho privátní klíč.

### <a name="obtaining-a-trusted-certificate"></a>Získání důvěryhodného certifikátu

Důvěryhodný certifikát je vystavený certifikační autority (viz [certifikační úřady na webu Wikipedia](https://en.wikipedia.org/wiki/Certificate_authority) pozadí). Podobně jako získávání identifikační karty government, vydání důvěryhodného certifikátu zahrnuje další proces a možné poplatky, ale ověřuje pravost žádosti a žadatel.

Klíčové pole, která musí být v certifikátu je plně kvalifikovaný název domény počítače R server. Certifikační autority vyžaduje ověření, že máte oprávnění k vytvoření nového serveru pro doménu, ke které patří server.

Pro další informace viz [certifikáty s veřejným klíčem](https://en.wikipedia.org/wiki/Public_key_certificate) na webu Wikipedia.

## <a name="install-an-ssl-certificate-on-windows"></a>Nainstalujte certifikát SSL v systému Windows

Certifikát SSL musí být nainstalován ručně na systému windows. Postupujte podle pokynů k instalaci certifikátu protokolu SSL.

### <a name="obtaining-a-self-signed-certificate-windows"></a>Získat certifikát podepsaný svým držitelem (Windows)

Tuto část přeskočte, pokud máte důvěryhodných certifikátů. Porovnání s certifikát od důvěryhodné autority, jako je vytváření identifikační karty pro sami je certifikát podepsaný svým držitelem. Tento proces je, kurzu mnohem jednodušší než práce s důvěryhodnou autoritou, ale také chybí silné ověřování, což znamená, že útočník můžete nahradit vlastní certifikát pro certifikát bez znaménka zaznamenat veškerý síťový provoz mezi klientem a Server. Proto *certifikát podepsaný svým držitelem by se používat pouze pro testování scénářů, v důvěryhodné síti a nikdy v produkčním prostředí.*

Z tohoto důvodu RTVS vždy vydá následující upozornění při připojování k serveru s certifikát podepsaný svým držitelem:

![Dialogové okno s upozorněním certifikát podepsaný svým držitelem](media/workspaces-remote-self-signed-certificate-warning.png)

Vystavit certifikát podepsaný svým držitelem:

1. Přihlaste se k počítači serveru R pomocí účtu správce.
1. Otevřete nový příkazový řádek správce prostředí PowerShell a vydejte následující příkaz, nahraďte `"remote-machine-name"` s plně kvalifikovaný název domény počítače serveru.

    ```ps
    New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "remote-machine-name"
    ```

1. Pokud jste spustili nikdy prostředí Powershell před na počítači serveru R, spusťte následující příkaz, kterým povolíte spouštění příkazů explicitně:

    ```ps
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
    ```

Pro informace viz [certifikáty podepsané svým držitelem](https://en.wikipedia.org/wiki/Self-signed_certificate) na webu Wikipedia.

### <a name="installing-the-certificate"></a>Instalace certifikátu

Pokud chcete nainstalovat certifikát na vzdáleném počítači, spusťte `certlm.msc` (Správce certifikátů) z příkazového řádku. Klikněte pravým tlačítkem na **osobní** složky a vyberte **všechny úlohy > Import** příkaz:

![Příkaz Import certifikátu](media/workspaces-remote-certificate-import.png)

### <a name="granting-permissions-to-read-the-ssl-certificates-private-key"></a>Udělení oprávnění ke čtení privátní klíč certifikátu SSL

Jakmile je certifikát importován, udělte `NETWORK SERVICE` účet oprávnění ke čtení privátní klíč, jak je popsáno v následujících pokynech. `NETWORK_SERVICE` slouží ke spouštění zprostředkovatel služby R, což je služba, která ukončí příchozí připojení SSL k počítači serveru k účtu.

1. Spustit `certlm.msc` (Správce certifikátů) z příkazového řádku správce.
1. Rozbalte položku **osobní > Certifikáty**, klikněte pravým tlačítkem na certifikát a vyberte **všechny úlohy > Spravovat privátní klíče**.
1. Klikněte pravým tlačítkem na certifikát a vyberte příkaz Spravovat privátní klíče v části všechny úlohy
1. V dialogovém okně se zobrazí, vyberte **přidat** a zadejte `NETWORK SERVICE` jako název účtu:

    ![Dialogové okno privátního klíče, přidání služba NETWORK_SERVICE spravovat](media/workspaces-remote-manage-private-key-dialog.png)

1. Vyberte **OK** dvakrát k zavření v dialogových oknech a potvrďte změny.

## <a name="install-an-ssl-certificate-on-ubuntu"></a>Na Ubuntu nainstalovat certifikát SSL

`rtvs-daemon` Balíček nainstaluje certifikát podepsaný svým držitelem ve výchozím nastavení jako součást instalace.

### <a name="obtaining-a-self-signed-certificate-ubuntu"></a>Získat certifikát podepsaný svým držitelem (Ubuntu)

Naleznete v popisu windows výhod a rizik použití certifikátu podepsaného svým držitelem. `rtvs-daemon` Balíček generuje a nakonfiguruje certifikát podepsaný sám sebou během instalace. Musíte provést pouze v případě, že chcete nahradit automaticky vygeneruje certifikát podepsaný svým držitelem.

K vydání svým certifikátu podepsaného držitelem sami:

1. SSH nebo přihlášení k počítači systému linux.
1. Nainstalujte `ssl-cert` balíčku:
    ```sh
    sudo apt-get install ssl-cert
    ```
1. Spustit `make-ssl-cert` k vygenerování certifikátu SSL podepsaného výchozí:
    ```sh
    sudo make-ssl-cert generate-default-snakeoil --force-overwrite
    ```
1. Generovaný klíč a soubory PEM převeďte PFX. Vygenerovaný soubor PFX musí být ve vaší domovské složky:
    ```sh
    openssl pkcs12 -export -out ~/ssl-cert-snakeoil.pfx -inkey /etc/ssl/private/ssl-cert-snakeoil.key -in /etc/ssl/certs/ssl-cert-snakeoil.pem -password pass:SnakeOil
    ```

### <a name="configuring-rtvs-daemon"></a>Konfigurace RTVS démon

Cesta k souboru certifikátu protokolu SSL (cesta k PFX) musí být nastavena v `/etc/rtvs/rtvsd.config.json`. Aktualizace `X509CertificateFile` a `X509CertificatePassword` s heslo a cesta k souboru v uvedeném pořadí.

```json
{
  "logging": { "logFolder": "/tmp" },
  "security": {
    "allowedGroup": "",
    "X509CertificateFile": "/etc/rtvs/ssl-cert-snakeoil.pfx",
    "X509CertificatePassword": "SnakeOil"
  },
  "startup": { "name": "rtvsd" },
  "urls": "https://0.0.0.0:5444"
}
```

Uložte tento soubor a restartujte démona, `sudo systemctl restart rtvsd`.

## <a name="install-r-services-on-windows"></a>Nainstalujte R služby v systému Windows

Pokud chcete spustit kódu jazyka R, musí mít vzdálený počítač R překladač nainstalovat následujícím způsobem:

1. Stáhněte a nainstalujte jednu z těchto možností:

    - [Otevřete Microsoft R](https://mran.microsoft.com/open/)
    - [CRAN r. pro Windows](https://cran.r-project.org/bin/windows/base/)

    Oba mají stejné funkce, ale Microsoft R otevřete výhody z další hardware accelerated lineární algebra knihovny laskavým svolením [Intel matematické jádra knihovny](https://software.intel.com/intel-mkl).

1. Spustit [instalační program služby R](https://aka.ms/rtvs-services) a restartovat po zobrazení výzvy. Instalační program provede následující akce:

    - Vytvořte složku v `%PROGRAMFILES%\R Tools for Visual Studio\1.0\` a zkopírujte všechny požadované binární soubory.
    - Nainstalujte `RHostBrokerService` a `RUserProfileService` a nakonfigurovat na automatické spouštění.
    - Konfigurace `seclogon` automatické spouštění.
    - Přidat `Microsoft.R.Host.exe` a `Microsoft.R.Host.Broker.exe` do brány firewall příchozí pravidla na výchozím portu 5444.

R služby spustit automaticky při restartování počítače:

- **Služba Service Broker hostitele R** zpracovává všechny přenosy HTTPS mezi proces a Visual Studio, kde kód R spouští v počítači.
- **Služba profil uživatele R** je privilegované komponenty, která zpracovává vytvoření profilu uživatele systému Windows. Služba je volána, když nový uživatel poprvé přihlásí k počítači serveru R.

Zobrazí se tyto služby v konzole pro správu služeb (`compmgmt.msc`).

## <a name="install-r-services-on-linux"></a>Nainstalujte R služby v systému Linux

Pokud chcete spustit kódu jazyka R, musí mít vzdálený počítač R překladač nainstalovat následujícím způsobem:

1. Stáhněte a nainstalujte jednu z těchto možností:

    - [Otevřete Microsoft R](https://mran.microsoft.com/open/)
    - [CRAN r. pro Windows](https://cran.r-project.org/bin/linux/ubuntu/)

    Oba mají stejné funkce, ale Microsoft R otevřete výhody z další hardware accelerated lineární algebra knihovny laskavým svolením [Intel matematické jádra knihovny](https://software.intel.com/intel-mkl).

1. Postupujte podle pokynů [vzdálené služby R pro Linux](setting-up-remote-r-service-on-linux.md), který obsahuje fyzické počítače Ubuntu virtuálních počítačích Azure Ubuntu, subsystému Windows pro Linux (WSL) a Docker kontejnery, včetně těch, které spuštěné v kontejneru úložiště Azure.

## <a name="configure-r-services"></a>Konfigurace služby R

S R služby spuštěné na vzdáleném počítači můžete také potřebovat vytvořit uživatelské účty, nastavte pravidla brány firewall, konfigurace sítí Azure a nakonfigurovat certifikát SSL.

1. Uživatelských účtů: vytvoření účtů pro každého uživatele, který má přístup k vzdálenému počítači. Můžete vytvořit buď standardní (bez oprávnění) místní uživatelské účty, nebo můžete připojení počítače R server k vaší doméně a přidat do příslušných skupin zabezpečení k `Users` skupiny zabezpečení.

1. Pravidla brány firewall: ve výchozím nastavení, `R Host Broker` naslouchá na portu TCP 5444. Proto se ujistěte, že jsou povolené pro příchozí a odchozí přenosy pravidla brány firewall systému Windows (odchozí je vyžadována pro instalaci balíčků a podobné scénáře).  Instalační program služby R Nastaví tato pravidla automaticky pro předdefinované bránu Windows firewall. Pokud používáte bránu firewall jiného výrobce, ale otevřít port 5444 pro `R Host Broker` ručně.

1. Konfigurace Azure: Pokud vzdálený počítač je virtuální počítač na platformě Azure, otevřete port 5444 pro příchozí provoz v rámci Azure sítě jako dobře, která je nezávislá brány Windows Firewall. Podrobnosti najdete v tématu [filtrování provozu sítě s skupinu zabezpečení sítě](https://docs.microsoft.com/azure/virtual-network/virtual-networks-nsg) v dokumentaci k Azure.

1. Řekněte zprostředkovatele hostitele R načíst certifikát SSL, které: Pokud instalujete certifikát na intranetový server, je pravděpodobné, že plně kvalifikovaný název domény serveru je stejná jako její název pro rozhraní NETBIOS. V takovém případě není nic, je třeba provést, protože to je výchozí certifikát, který je načten.

    Ale pokud nainstalujete certifikát na straně Internetu serveru (například virtuální počítač Azure), použijte plně kvalifikovaný název domény (FQDN) serveru, protože je plně kvalifikovaný název domény internetového serveru nikdy stejná jako její název pro rozhraní NETBIOS.

    Chcete-li použít plně kvalifikovaný název domény, přejděte na nainstalovanou R služby (`%PROGRAM FILES%\R Remote Service for Visual Studio\1.0` ve výchozím nastavení), otevřete `Microsoft.R.Host.Broker.Config.json` soubor v textovém editoru a nahraďte jeho obsah CN následující, přiřazení k ať váš server je plně kvalifikovaný název domény, například `foo.westus.cloudapp.azure.com`:

    ```json
    {
      "server.urls": "https://0.0.0.0:5444",
      "security": {
        "X509CertificateName": "CN=your-server-fully-qualified-domain-name"
      }
    }
    ```

    Uložte tento soubor a restartujte počítač a změny.

## <a name="troubleshooting"></a>Poradce při potížích

**V počítači serveru R nereaguje, co dělat?**

Zkuste příkazem ping otestovat vzdáleného počítače z příkazového řádku: `ping remote-machine-name`. Pokud se příkazem ping nezdaří, zkontrolujte, zda že počítač běží.

**Q. Interaktivní okno R uvádí vzdálený počítač je zapnuté, ale proč neběží služba?**

Existují tři možné důvody:

- [Rozhraní .NET framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981) nebo vyšší není nainstalován v počítači.
- Brány firewall pravidla pro `Microsoft.R.Host.Broker` a `Microsoft.R.Host` pro příchozí a odchozí připojení na portu 5444 není povolen.
- Certifikát SSL s `CN=<remote-machine-name>` nebyl nainstalován.

Restartujte počítač po změnách výše. Potom zkontrolujte, zda `RHostBrokerService` a `RUserProfileService` běží prostřednictvím buď Správce úloh (kartě služeb) nebo `services.msc`.

**Q. Proč interaktivních okna R říká "401 Přístup odepřen" při připojování k serveru R?**

Existují dvě možné příčiny:

- Je velmi pravděpodobné, který `NETWORK SERVICE` účet nemá přístup k privátnímu klíči certifikátu protokolu SSL. Podle předchozích pokynů udělit `NETWORK SERVICE` přístup k privátnímu klíči.
- Ujistěte se, že `seclogon` se službou. Použití `services.msc` konfigurace `seclogon` na automatické spouštění.

**Q. Proč interaktivních okna R říká "404 nebyl nalezen" při připojování k serveru R?**

Tato chyba je pravděpodobně z důvodu chybějícího knihovny jazyka Visual C++ redistributable. Zkontrolujte interaktivní okno R a zobrazit, pokud je zpráva týkající se chybějící library(DLL). Potom zkontrolujte, zda VS 2015 redistributable je nainstalován, a zda máte R nainstalované také.

**Q. Nemám přístup k Internetu nebo prostředků z okna interaktivní R, co mám udělat?**

Ujistěte se, že pro pravidla brány firewall `Microsoft.R.Host.Broker` a `Microsoft.R.Host` povolit odchozí přístup na portu 5444. Restartujte počítač po použití změny.

**Q. I jste se pokusili těchto řešení a i přesto nefunguje. Co teď?**

Hledat v souborech protokolu v `C:\Windows\ServiceProfiles\NetworkService\AppData\Local\Temp`. Tato složka obsahuje samostatné soubory protokolu pro každou instanci služba Service Broker R, která byla spuštěna. Nový soubor protokolu se vytvoří při každém restartu služby. Zkontrolujte poslední protokolový soubor, který následuje co může být špatně.
