---
title: Skapa en ny transporthanteringsmotor
description: I det här avsnittet beskrivs hur du skapar en ny transporthanteringsmotor i Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSGenericEngine, TMSRateEngine, TMSMileageEngine, TMSEngineParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 51661
ms.assetid: 0473acef-755e-4b42-acf5-5e5aa902dc0e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be52c6afb66e88b36f3b2cdf5af14e17b3d3005f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678134"
---
# <a name="create-a-new-transportation-management-engine"></a>Skapa en ny transporthanteringsmotor

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny transporthanteringsmotor i Dynamics 365 Supply Chain Management. 

Transporthanteringsmotorer (TMS) definierar logiken som används för att generera och bearbeta transporttariffer i Transporthantering. Supply Chain Management innehåller flera olika motortyper som beräknar olika parametrar, till exempel priser, transittider och antalet zoner som ska passeras under transport. I den här artikeln förklaras hur du använder Microsoft Visual Studio utvecklingsmiljö tillsammans med utvecklingsverktyg för Supply Chain Management för att skapa och distribuera en ny TMS-motor, och sedan hur du ställer in motorerna i Operations. Mer information om motorer finns i [Transporthanteringsmotor](transportation-management-engines.md).

## <a name="create-a-new-tms-engine"></a>Skapa en ny TMS-motor

I det här avsnittet beskrivs hur du skapar ett klassbibliotek med en TMS-motorimplementering och hur du refererar till det från en Supply Chain Management-modell.

1. För att distribuera dina nya motorer måste du ha en modell som innehåller motorerna. I menyn **Dynamics 365** &gt; **Modellhantering**, klicka på **Skapa modell** för att skapa en ny modell. På första sidan i guiden **Skapa modell** ge modellen namnet **TMSEngines**. 

   [![Skapa en modell.](./media/012.png)](./media/012.png)

2. På nästa sida väljer du **Skapa nytt paket**. 

   [![Skapa ett nytt paket.](./media/021.png)](./media/021.png)

3. På nästa sida väljer du den **ApplicationSuite**-modell som ska refereras. (Den **ApplicationPlatform**-modellen är förvald.) 

   [![Välja modellen som referens.](./media/032.png)](./media/032.png)

4. På nästa sida klickar du på **Slutför** om du vill bekräfta att du skapat en ny modell. 

   [![Slutföra modellgenerering.](./media/042.png)](./media/042.png)

5. I en ny lösning skapar du ett nytt Supply Chain Management-projekt och namnger **TMSThirdParty**. I projektegenskaperna ställer du in projektets modell på **TMSEngines**.
6. Lägg till ett nytt C\#-klassbibliotek i lösningen och namnge det till **ThirdPartyTMSEngines**.
7. I ThirdPartyTMSEngines-projektet lägger du till referenser till Supply Chain Management-specifika sammansättningar:
   -   Appsammansättningar som gör att X++-typer kan refereras. Dessa sammansättningar finns på följande platser. \[Paketroten\] är sökvägen till platsen där alla distribuerade lösningen placeras, t.ex. C:\\Paket.

        ```xpp
        [Packages root]\ApplicationPlatform\bin\Dynamics.AX.ApplicationPlatform.dll
        [Packages root]\ApplicationFoundation\bin\Dynamics.AX.ApplicationFoundation.dll
        [Packages root]\ApplicationSuite\bin\Dynamics.AX.ApplicationSuite.dll
        ```
        
   -   Framework-sammansättningar som möjliggör åtkomst till data, LINQ och extrafunktioner. Alla dessa samlas kan finnas i \[Paketroten\]\\binge.

        ```xpp 
        Microsoft.Dynamics.ApplicationPlatform.Environment.dll
        Microsoft.Dynamics.AX.Data.Core.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.AdoNet.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Msil.dll
        Microsoft.Dynamics.AX.Server.Core.dll
        Microsoft.Dynamics.AX.Xpp.AxShared.dll
        Microsoft.Dynamics.AX.Xpp.Support.dll
        ```

   -   Kärn-TMS-enheten (som innehåller motorer) och TMS-basenheten (som innehåller hjälpare, konstanter, klassdefinitioner för dataöverföring och så vidare). Dessa sammansättningar finns på följande platser.

        ```xpp
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.dll
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.Base.dll
        ```
8. Byt namn på C\#-klassen som genereras automatiskt i ThirdPartyTMSEngines-projektet till **SampleRatingEngine**.
9. Implementera motor. Eftersom vi skapar en tariffmotor i det här exemplet, ärver vi från basklassen för tariffmotorer. Basklassen implementerar det mesta av satsmotorgränssnittet (**TMSFwkIRateEngine**). Vi måste bara implementera tariffmetod. För att hålla detta exempel enkelt gör vi att den här metoden registrerar en hårdkodad kurs på 100. Du kan skapa dessa funktioner för att implementera något av motorgränssnitten, till exempel **TMSFwkIAccessorialEngine**. Alla motorgränssnitt definieras i X++.

    ```xpp
    namespace ThirdPartyTMSEngines
    {
        using Dynamics.AX.Application;
        using Microsoft.Dynamics.Ax.Tms.Base.Data;
        using Microsoft.Dynamics.Ax.Tms.Base.Utility;
        using Microsoft.Dynamics.Ax.Tms.Bll;
        using System.Xml.Linq;
        public class SampleRatingEngine : BaseRateEngine
        {
            public override RatingDto rate(TmsTransactionFacade transactionFacade, XElement shipment, TMSRateMasterCode rateMasterCode)
            {
               XElement re = shipment.RetrieveOrCreateRatingEntity(this.RatingDto);
               re.AddRate(TmsRateType.Rate, 100);
               return this.RatingDto;
            }
        }
    }
    ```

10. Skapa lösningen.
11. Lägg till en ny referens till TMSThirdParty-projekt. Referensen bör peka på ThirdPartyTMSEngines-projektet. När du är klar ska lösningen se ut så här. 

    [![Lösningen, som innehåller en referens till TMSThirdParty-projektet.](./media/052.png)](./media/052.png)

12. Skapa lösningen. Kontrollera att det nya biblioteket visas i noden **Referenser** i Programutforskaren. 

    [![Det nya biblioteket i Programutforskaren referensnod.](./media/061.png)](./media/061.png)

## <a name="deploy-the-tms-engine-as-a-package"></a>Distribuera TMS-motor som ett paket

Ett sätt att distribuera tredjeparts TMS-motorer är genom ett distributionspaket. Den här metoden rekommenderas i en produktionsmiljö. I en utvecklingsmiljö kan du manuellt kopiera sammansättningarna, som beskrivs i nästa avsnitt, "Konfigurera en TMS-motor i Supply Chain Management." Följ dessa steg för att distribuera motorn som ett paket.

1. I menyn **Dynamics 365** &gt; **Distribuera** klicka på <strong>Skapa distributionspaket</strong>.
2. I dialogrutan **Skapa distributionspaket** välj TMSEngines modell och ange sökvägen där du vill lagra dina paketfiler. 

   [![Välja TMSEngines modell.](./media/071.png)](./media/071.png)

3. Nu kan du distribuera paketet till målmiljön. Mer information finns i [Installera ett paket som kan distribueras](../../fin-ops-core/dev-itpro/deployment/install-deployable-package.md).

## <a name="set-up-the-tms-engine-in-supply-chain-management"></a>Ställa in TMS-motor i Supply Chain Management

I det här avsnittet beskrivs hur du ställer in Supply Chain Management till att använda en TMS-motor, och visar hur den nya motor som vi skapar används vid fraktprissökning. Exemplet i det här avsnittet använder demonstrationsföretaget USMF.

1. Skapa en ny motor enligt beskrivningen i avsnittet "Skapa en ny TMS-motor".
2. Skapa din lösning.
3. Kopiera den resulterande monteringen till den binära platsen för Supply Chain Management-servern, \[AOSWebRoot\]bin. **Obs!** Det här steget är endast relevant i utvecklingsmiljöer. I en produktionsmiljö bör du distribuera via ett distributionspaket. Instruktioner finns i föregående avsnitt, "Distribuera TMS-motorn som ett paket."
4. I Supply Chain Management, på sidan **Tariffmotorer** skapa en ny tariffmotor. Motorn bör peka mot den motorsamling som produceras genom att du bygger motorklassbiblioteket och den motorklass som du har implementerat. 

   [![Skapa en ny tariffmotor på sidan Tariffmotorer.](./media/081.png)](./media/081.png)

5. Skapa ett transportföretag som använder exempeltariffmotor. Eftersom vår motor inte använder några data behöver du inte tilldela ett tariffhuvud. 

   [![Skapa ett nytt transportföretag.](./media/092.png)](./media/092.png)

6. På sidan **workbench för tariff/rutt** klickar du på **Tariffbutik**. Du bör se en tariff på 100,00 från SampleCarrier, enligt bilden nedan. I det här exemplet handlar vi om en rutt från lagerställe 24 till kunden US-004. Men eftersom tariffen är hårdkodad ser du alltid en kurs på 100,00.

   [![Ruttworkbench för tariff.](./media/101.png)](./media/101.png)

## <a name="tips-and-tricks"></a>Tips och trick

- Om du använder utvecklingsverktyg för Supply Chain Management är det praktiskt att lägga till ett nytt projekt till din lösning. Om du anger projektet som ett startprojekt och startar en felsökningssession, kan du felsöka både X++ och C\# koden i samma felsökningssession.
- Varje gång du ändrar och kompilera om ditt ThirdPartyTMSEngines-projekt måste du manuellt kopiera den resulterande monteringen till den binära platsen eller distribueras via ett distributionspaket. Annars kan du köra en föråldrad sammansättning.
- När du har utfört TMS-specifika operationer i Supply Chain Management, kan Internet Information Services (IIS)-arbetsprocessen låsa ThirdPartyTMSEngines-sammansättningen så att sammansättningen inte kan uppdateras. Starta i så fall om processen w3svc.

### <a name="whitepaper"></a>Dokumentation

För mer information, ladda ner följande dokumentation (skriven till stöd för AX2012, men gäller fortfarande Dynamics 365 Supply Chain Management)

- [Implementera och distribuera Transporthanteringsmotorer](https://download.microsoft.com/download/b/5/f/b5ff8fef-3918-4c1d-92d5-b67eb0971684/ImplementingAndDeployingTransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]