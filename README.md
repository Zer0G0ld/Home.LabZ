# Home.LabZ

> Meu homelab pessoal e privado para aprendizado, armazenamento, mídia e segurança.

---

## Objetivo

O objetivo deste projeto é criar um servidor pessoal para:

- Aprender sobre Linux, Docker e redes.
- Ter controle total dos serviços e dados.
- Hospedar Nextcloud, Pi-hole, Jellyfin, Vaultwarden e outros.
- Garantir privacidade, segurança e acesso remoto via VPN.

---

## Topologia do Homelab

```
                           Internet
                               │
                           VPN (TailScale)
                               │
                    ┌──────────┴───────────┐
                    │ Roteador / Firewall  │
                    │  (Pi-hole opcional)  │
                    └──────────┬───────────┘
                               │
                   ┌───────────┼───────────┐
                   │                       │
             ┌─────┴─────┐           ┌─────┴───────┐
             │   PC /    │           │   Notebook  │
             │ Servidor  │           │  (opcional) │
             │ Umbrel OS │           └─────────────┘
             └─────┬─────┘
                   │
        ┌──────────┼───────────┐
        │          │           │
   ┌────┴────┐ ┌───┴─────┐ ┌───┴───────┐
   │Nextcloud│ │ Jellyfin│ │Vaultwarden│
   │ (Drive  │ │ (Mídia) │ │ (Senhas)  │
   │ Privado)│ │         │ │           │
   └─────────┘ └─────────┘ └───────────┘

```

---

## Serviços Principais

### Nextcloud
- Armazenamento de arquivos e backups.
- SSL via Let's Encrypt.
- Configurar limites de upload e quotas.
- Pode usar discos externos se necessário.

### Pi-hole
- Bloqueia anúncios para toda a rede.
- Melhor se colocado no roteador.
- Configure fallback DNS apenas para rede interna.

### Jellyfin
- Streaming de filmes, séries e músicas.
- SSD e RAM recomendados para desempenho.
- Acesso externo via VPN ou reverse proxy com SSL.

### Vaultwarden
- Gerenciador de senhas local ou na rede Tor.
- Manter backups criptografados.
- Não expor sem VPN.
- Sempre atualizar para segurança.

---

## Privacidade e Segurança

- Navegadores: Librewolf ou Brave.
- Buscas: DuckDuckGo ou Startpage.
- Emails privados: ProtonMail ou Tutanota.
- Criptografia de arquivos: VeraCrypt ou Cryptomator.
- VPN para acesso remoto seguro.
- Pi-hole + navegador bloqueando trackers.

---

## Estrutura de Arquivos

```

Home.LabZ/
├─ docker-compose.yml
├─ nextcloud-config/
├─ pihole-config/
├─ jellyfin-config/
├─ vaultwarden-config/
├─ README.md
└─ diagramas/

```

---

## Extras
- Backups automáticos (local ou nuvem).  
- Monitoramento de CPU, RAM e temperatura.  
- Automatização de atualizações de apps e do sistema.  

---

## Licença
- Conteúdo pessoal. Pode ser privado ou público.  
- Configurações sensíveis **não devem ser compartilhadas publicamente**.

