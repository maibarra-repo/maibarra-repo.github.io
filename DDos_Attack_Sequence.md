[![Markdown Diagram](https://mermaid.ink/img/pako:eNqFk9tu2kAQhl9ltLcFxNngi0hpUdVIbS-aRpUqbgZ7MKvYu-4eCA7Ku3fWJ1CoVG7sHf7555sZ71kkOiURC0t_PKmENhIzg8VWAcBOn-ALJs9k6iPcJ04buHfuKlaicTKRJSoHH7VT5Jo4qfRWsPn-2ASD8yddcLC6VX2Whl4wz2__-UU7S-bY1e5rdEjDu7uGIWZu2_KAQ5Pxw5aUyL1M3rt81brspN5KlQVMVmu9B6yNG134NTIuw5K4S0qlzby0lIJ0lnLOsvDS1QDLlLa2VFgQ5Fo_-xJMGLd1F2cWsG2PFjcQ1xbuQJzGXMoSON229W4SSjtWyezggPGv7PpXoFNJRvKuQ6t0SshaeQxgmIKTBdnGqU9grA_dSuIfDTc4g_swS1SYV1a2OZ2MU4aX2g8l_LzIq5zlYH1RoKn-A91-Itw25vKVwgzQQZiENMAuqECrTNc722jbrovDKWDi5BEd5yTaK0emILTe_Ku7vjl4KlMMKD4PtTQw-S7X7HgZU1hLuzw7arya1V1cHiyYYJPLQjr-KnZVPxgxEAWjoEz5yp1D-lZwNwVtRcyvKe3R524rtuqNpeidfqxUImJnPA2E0T47iHiPueWTr2Hb-9pHKZV8Sb81l7q-2wPBM_yt9UXDZxGfxUnEw8louZytosVyvR7PZ9NoPhCViJej1WQ9jmbLKBovp-vV6m0gXmuHyWgxXi_mi2g9mUXRfDqdvv0FhKpxDA?type=png)](https://mermaid.live/edit#pako:eNqFk9tu2kAQhl9ltLcFxNngi0hpUdVIbS-aRpUqbgZ7MKvYu-4eCA7Ku3fWJ1CoVG7sHf7555sZ71kkOiURC0t_PKmENhIzg8VWAcBOn-ALJs9k6iPcJ04buHfuKlaicTKRJSoHH7VT5Jo4qfRWsPn-2ASD8yddcLC6VX2Whl4wz2__-UU7S-bY1e5rdEjDu7uGIWZu2_KAQ5Pxw5aUyL1M3rt81brspN5KlQVMVmu9B6yNG134NTIuw5K4S0qlzby0lIJ0lnLOsvDS1QDLlLa2VFgQ5Fo_-xJMGLd1F2cWsG2PFjcQ1xbuQJzGXMoSON229W4SSjtWyezggPGv7PpXoFNJRvKuQ6t0SshaeQxgmIKTBdnGqU9grA_dSuIfDTc4g_swS1SYV1a2OZ2MU4aX2g8l_LzIq5zlYH1RoKn-A91-Itw25vKVwgzQQZiENMAuqECrTNc722jbrovDKWDi5BEd5yTaK0emILTe_Ku7vjl4KlMMKD4PtTQw-S7X7HgZU1hLuzw7arya1V1cHiyYYJPLQjr-KnZVPxgxEAWjoEz5yp1D-lZwNwVtRcyvKe3R524rtuqNpeidfqxUImJnPA2E0T47iHiPueWTr2Hb-9pHKZV8Sb81l7q-2wPBM_yt9UXDZxGfxUnEw8louZytosVyvR7PZ9NoPhCViJej1WQ9jmbLKBovp-vV6m0gXmuHyWgxXi_mi2g9mUXRfDqdvv0FhKpxDA)

# Description of diagram
 The Hacker decides to DDos  attack specific Webserver using a Botnet.  
 The Botnet disguised as Webserver starts sending DNS name lookup request.  
 The DNS answers the request and sends it to Webserver.
 The Webserver is being flooded with requests that it noticeably affects website load times.
 The Company that owns it sends for and receives an Ip traffic analysis of what is affecting load times.  
 The Company realizing that its a DDoS attack decides to rate limit DNS requests.
 The Firewall then proceeds to block excessive DNS requests.

## Diagram raw code

sequenceDiagram
   box Hacker
    Actor Attacker
    participant Botnet
    end
    participant DNS
    box Company
    participant Firewall
    participant Webserver
    end
    Attacker->>Botnet: Has Botnet target specific Webserver
    Loop Botnet using DNS spoof attack
        Botnet->>DNS: Botnet disguised itself as webserver sends DNS name lookup request
        DNS->>Webserver: DNS server sends the response to target
    end
    note right of Webserver: Webserver experiencing excessive load times
    Webserver->>+Firewall:Request traffic analysis
    Firewall->>-Webserver:Ip Traffic anaylsis summary
    note right of Webserver: Company realizes that  their is an ongoing DDos attack and activates countermeasures
    Webserver->>Firewall: Update rules to Ip block excessive DNS requests.
    DNS->>Firewall: Is rate limited by Firewall
