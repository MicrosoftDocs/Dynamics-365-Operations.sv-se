---
title: Fel på certifieringssökväg när du ställer in appanslutning
description: Om felmeddelandet "Förtroendeankare för certifieringsväg hittades inte" visas i Warehouse Management-appen använder du den här sidan för att lösa eller undvika problemet.
author: ivanv-microsoft
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: WMA
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e4a36874ac4982c9c92a7dcc17c13c7c7c02bf8c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477635"
---
# <a name="trust-anchor-for-certification-path-not-found-when-setting-up-app-connection"></a>Förtroendeankare för certifieringssökväg hittas inte när du ställer in appanslutning

## <a name="symptoms"></a>Symtom

När du försöker ansluta till Supply Chain Management kan Warehouse Management-appen visa följande felmeddelande:

> java.security.cert.certPathValidatorException: Förtroendeankare för certifieringsväg hittades inte.

Det här problemet kan påverka enheter med följande egenskaper:

- **OS-version**: Android 4.4.x (som Zebra TC55). Detta är inte ett problem i tidigare Android-versioner.
- **Supply Chain Management-plats**: Molnet
- **Anslutningsläge**: Klienthemlighet eller certifikat

## <a name="possible-cause"></a>Möjlig orsak

Microsoft kan ha uppdaterat serverns SSL-certifikat som används i Supply Chain Management. Därför kan rotcertifikatet och/eller ett av de mellanliggande certifikaten ha ändrats, så att det nya certifikatet inte finns med i listan över betrodda systemcertifikat för den mobila enheten. Nyare versioner av Android automatisk uppdaterar listorna över betrodda certifikat, men Android 4.4.x gör det inte.

## <a name="resolution"></a>Lösning

Gör något att väljande för att lösa problemet:

- Använd lösningen som beskrivs i nästa avsnitt för att uppdatera varje relevant enhet.
- Det *kan* vara möjligt att kontakta Zebra eller Google för att få en uppdatering av certifikaten från den systembetrodda certifikatutfärdaren (CA). Vi har dock inte bekräftat detta.
- Överväg om möjligt att ersätta äldre enheter med enheter som kör en nyare version av Android (där betrodda CA-certifikat uppdateras automatiskt).

### <a name="workaround"></a>Lösning

#### <a name="step-1-export-the-new-root-certificate-from-supply-chain-management"></a>Steg 1: Exportera det nya rotcertifikatet från Supply Chain Management

Hämta det nya rotcertifikatet manuellt med hjälp av webbläsaren genom att göra följande:

1. Logga in i Dynamics Supply Chain Management och öppna startsidan.

1. Öppna dialogrutan **Platsen är säker** genom att välja låsikonen i adressfältet i webbläsaren.
1. Välj **Certifikat (giltigt)** i dialogrutan för att öppna fönstret **Certifikat** för detta certifikat.
1. Öppna fliken **Certifieringsväg** i fönstret **Certifikat**.
1. Välj det översta certifikatet som visas i hierarkin. (detta är rotcertifikatet).
1. Öppna fliken **Detaljer** i fönstret **Certifikat**.
1. Välj knappen **Kopiera till fil** längst ned på fliken **Detaljer**.
1. **Guiden för certifieringsexport** öppnas. Klicka på **Nästa** när du vill fortsätta.
1. Sidan **Exportfilformat** öppnas. Välj **DER-kodad binär X.509 (.CER)**. Välj **Nästa** för att fortsätta.
1. Sidan **Filer som ska exporteras** öppnas, ange ett filnamn och en plats. Välj **Nästa** för att fortsätta.
1. Sidan med **guiden för att slutföra certifikatexporten** öppnas och visar resultatet av exporten Välj **Slutför**.

#### <a name="step-2-install-the-downloaded-certificate-onto-the-affected-devices"></a>Steg 2: Installera det nedladdade certifikatet på de enheter som påverkas

Installera det nedladdade certifikatet genom att göra följande:

1. Överför certifikatet som du laddade ned i det föregående steget till enheten du vill uppdatera. Du kan till exempel använda ett SD-kort eller en nätverksanslutning för att göra filen tillgänglig för enheten.
1. Öppna säkerhetsinställningarna för din enhet och välj menyalternativet för att installera ett certifikat från en fil. (De exakta stegen för detta varierar beroende på enhet och OS-version.)
1. Det nya certifikatet ska nu visas på fliken **Användare** för betrodda certifikat.
1. Upprepa den här proceduren för varje berörd enhet.
