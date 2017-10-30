```
VLAN Control Utility:

::: Usage:

vlanctl

        --if <if_name> Sets the target Interface of a composite vlanctl command to <if_name>.

        --rx Sets the direction of a composite vlanctl command to RECEIVE

        --tx Sets the direction of a composite vlanctl command to TRANSMIT

        --tags <nbr_of_tags> Sets the number of tags of a composite vlanctl command to <nbr_of_tags>

        --if-create <real_if_name> <if_index> Creates a new VOPI named <real_if_name>.v<if_index> and attaches it to the real device
         <real_if_name>. For instance, if this command were executed for the eth0 real interface and the VOPI interface index were
         set to 3, the resulting interface would have been named eth0.v3.

        --if-create-name <real_if_name> <vlan_if_name> Creates a new VOPI named <vlan_if_name> and attaches it to the real device

        --if-delete <vlan_if_name> Destroy the VOPI named <vlan_if_name>.

        --rule-append Inserts a new Tagging Rule as the last rule of the specified Tagging Rule Table. Dependencies: --if, --rx or
         --tx, and --tags.

        --rule-insert-before <rule-id> Inserts a new Tagging Rule before the Tagging Rule whose identifier matches <rule-id> in the
        specified Tagging Rule Table. Dependencies: --if, --rx or --tx, and --tags.

        --rule-insert-after <rule-id> Inserts a new Tagging Rule after the Tagging Rule whose identifier matches <rule-id> in the
        specified Tagging Rule Table. Dependencies: --if, --rx or --tx, and --tags.

        --rule-remove <rule-id> Removes the Tagging Rule that matches <rule-id> from the specified Tagging Rule Table. Dependencies:
        --if, --rx or --tx, and --tags.

        --rule-remove-all <real_if_name> <vlan_if_name> Removes all the Tagging Rules for the vlan device.

        --show-table Lists all Tagging Rules stored in the specified Tagging Rule Table. Dependencies: --if, --rx or --tx, and
        --tags.

        --all Lists all Tagging Rules. Dependencies: --if.

        --default-tpid <tpid> Sets the default TPID value of a tagging rule table to <tpid>. When a table is created, its default
        TPID value is set to 0x8100. Dependencies: --if, --rx or --tx, and --tags.

        --default-pbits <pbits> Sets the default PBITS value of a tagging rule table to <pbits>. When a table is created, its
        default PBITS value is set to 0. Dependencies: --if, --rx or --tx, and --tags.

        --default-cfi <cfi> Sets the default CFI value of a tagging rule table to <cfi>. When a table is created, its default CFI
        value is set to 0. Dependencies: --if, --rx or --tx, and --tags.

        --default-vid <vid> Sets the default VID value of a tagging rule table to <vid>. When a table is created, its default VID
        value is set to 1 (as per IEEE 802.1Q). Dependencies: --if, --rx or --tx, and --tags.

        --cfg-dscp2pbits <dscp> <pbits> Programs the entry number <dscp> of the DSCP-TO-PBITS translation table of a Real Device to
        the value specified by <pbits>. When a tagging rule table is created, the default values of the DSCP-TO-PBITS table are
        set by copying the lowest 3 bits of each DSCP value as the PBITS value, for each entry in the table. For instance, the
        following entries are programmed by default: DSCP=5:PBITS=5, DSCP=15:PBITS=7, etc. The DSCP-TO-PBITS translation table
        has 64 entries. Dependencies: --if.

        --show-dscp2pbits Lists the values programmed in the DSCP-TO-PBITS table of the specified Real Device. Dependencies:
        --if.

        --cfg-tpid <tpid0> <tpid1> <tpid2> <tpid3> Configures the TPID Table entries of a given Real Interface. The configured
        TPID values are used to identify VLAN Headers of packets received from and transmitted to the VOPIs created for a given
        Real Interface. Four values must always be specified. The default TPID values are 0x8100, 0x8100, 0x8100, and 0x8100.
        Dependencies: --if.

        --show-tpid Lists the values programmed in the TPID Table of the specified Real Device. Dependencies: --if.

        --local-stats <vlan_if_name> Shows the statistics counters maintained for the VOPI named <vlan_if_name>. These counters
        are complimentary to the standard counters maintained for the device, which can be read via the Linux ifconfig
        command.

        --filter-ethertype <ethertype> Match the Ethertype field in the Ethernet Header of incoming frames against <ethertype>.

        --filter-pbits <pbits> <tag_nbr> Match the PBITS value of VLAN Header number <tag_nbr> of incoming frames against
        <pbits>.

        --filter-cfi <cfi> <tag_nbr> Match the CFI bit of VLAN Header number <tag_nbr> of incoming frames against <cfi>.

        --filter-vid <vid> <tag_nbr> Match the VID value of VLAN Header number <tag_nbr> of incoming frames against <vid>.

        --filter-tag-ethertype <ethertype> <tag_nbr> Match the Ethertype field of the VLAN Header number <tag_nbr> of incoming
        frames against <ethertype>.

        --filter-dscp <dscp> Match the DSCP value in the IPv4 header of incoming frames against <dscp>.
        --filter-rxif <real_if_name> Match the rx VOPI of the transmitting packet against <real-if-name>. This filter can be used to bind a Tagging
        Rule to a specific rx VOPI on the TRANSMIT direction. This filter is not applicable for rules in the RECEIVE direction.

        --filter-txif <vlan_if_name> Match the transmitting VOPI against <vlan-if-name>. This filter can be used to bind a Tagging
        Rule to a specific VOPI on the TRANSMIT direction. This filter is not applicable for rules in the RECEIVE direction.
        TRANSMIT rules without this filter will apply to all frames transmitted from all VOPIs attached to the Real Device.

        --filter-skb-prio <priority> Match the SKB priority of incoming frames against <priority>.

        --filter-skb-mark-flowid <flowid> Match the Flow ID subfield of the SKB Mark field against <flowid>. The SKB Mark Flow ID
        subfield can be used as a way to correlate packet classification made by other Linux modules (such as ebtables and
        iptables) with Tagging Rules. A possible usage for this filter would be to direct packets generated by an application to
        a specific port of a real interface (such as a GPON port) based on layer 3 filters. In this example a socket would be
        created on a VOPI,IP Tables rules would be created to identify flows and set Flow IDs, and Tagging rules would be
        created to match on such Flow IDs and apply treatments, such as setting the destination GEM Port and Queue.

        --filter-skb-mark-port <port> Match the Port subfield of the SKB Mark field against <port>. This filter can be used to bind
         certain Tagging Rules with a specific Real Interface port (for instance a GPON Port).

        --filter-skb-gemport <gemport> Match the Gemport subfield of the SKB field against <gemport>. This filter can be used to bind
         certain Tagging Rules with a specific Real Interface port (for instance a GPON Port).

        --filter-vlan-dev-mac-addr <ignore_if_multicast> Match the recv frame dest MAC addr against the recv virtual interface.
         Set <ignore_if_multicast> to 0 to apply filter on all recv frames.
         Set <ignore_if_multicast> to 1 to apply filter on unicast frames only.
         This filter is not applicable for rules in the TRANSMIT direction.

        --pop-tag Remove the outermost VLAN tag. If multiple tags are to be removed, this treatment should be specified for each
        VLAN tag to be removed.

        --push-tag Add the default VLAN tag of the corresponding Tagging Rule Table as the new outer tag. The default TPID value
        will be used as the new Ethertype value in the Ethernet header, the existing Ethertype of the Ethernet Header will be used
        as the Tag Ethertype field of the new tag, and the default PBITS, CFI and VID will be used as the TCI of the new tag. If
        multiple tags are to be inserted, this treatment must be specified for each VLAN tag to be inserted.

        --set-ethertype <ethertype> Set the Ethertype value of the Ethernet Header to <ethertype>.

        --set-pbits <pbits> <tag_nbr> Set the PBITS value of the VLAN Header number <tag_nbr> to <pbits>.

        --set-cfi <cfi> <tag_nbr> Set the CFI bit of the VLAN Heade number <tag_nbr> to <cfi>.

        --set-vid <vid> <tag_nbr> Set the VID of the VLAN Header number <tag_nbr> to <vid>.

        --set-tag-ethertype <ethertype> Set the Ethertype field of the VLAN Header number <tag_nbr> to <ethertype>.

        --set-dscp <dscp> Set the IPv4 DSCP value of the matching frame to <dscp>.

        --copy-pbits <from_tag_nbr> <to_tag_nbr> Copy the PBITS value from VLAN Header number <from_tag_nbr> to VLAN Header number
        <to_tag_nbr>.

        --copy-cfi <from_tag_nbr> <to_tag_nbr> Copy the CFI value from VLAN Header number <from_tag_nbr> to VLAN Header number
        <to_tag_nbr>.

        --copy-vid <from_tag_nbr> <to_tag_nbr> Copy the VID value from VLAN Header number <from_tag_nbr> to VLAN Header number
        <to_tag_nbr>.

        --copy-tag-ethertype <from_tag_nbr> <to_tag_nbr> Copy the Ethertype value from VLAN Header number <from_tag_nbr> to VLAN
        Header number <to_tag_nbr>.

        --dscp2pbits <tag_nbr> Translate the IPv4 DSCP into a PIBTS value, and write the translated PBITS value in the VLAN Header
        number <tag_nbr>. The DSCP-To-PBITS table of the respective Real Device is used for translation.

        --set-rxif <vlan_if_name> Forward frames in the RECEIVE direction that match this rule to the VOPI specified in
        <vlan_if_name>. If not specified, the frame will be forwarded to a randomly chosen VOPI. Using this treatment in the
        TRANSMIT direction has no effect.

        --set-if-mode-ont Set real device mode to ONT.

        --set-if-mode-rg  Set real device mode to RG.

        --drop-frame Drop the matching frame.
        --set-skb-prio <priority> Set the SKB priority to <priority>.

        --set-skb-mark-port <port> Set the Port subfield of the SKB Mark field to <port>. The SKB Mark Port subfield is used by
        the Broadcom device drivers to send a frame to a specific port within a Real Interface. For instance, a GPON Real
        Interface may have been configured with multiple GEM Ports. When a packet is sent to that interface, the driver uses
        the SKB Mark Port subfield as the GEM Port to which the packets will be transmitted.

        --set-skb-gemport <gemport> Set the Gemport subfield of the SKB field to <gemport>. The SKB Gemport subfield is used by
        the MTK device drivers to send a frame to a specific gemport within a Real Interface.

        --set-skb-mark-queue <queue> Set the Queue subfield of the SKB Mark field to <queue>. The SKB Mark Queue subfield is used
        by the Broadcom device drivers to determine the queue to which transmit a frame.

        --set-skb-mark-flowid <flowid> Set the Flow ID subfield of the SKB Mark field to <flowID>. The SKB Mark Flow ID subfield
        can be used as a way to correlate packet classification made by Tagging Rules with other Linux modules (such as
        ebtables and iptables).

        --learn-vlan-and-pop-tag Learn vlan id of packets specified by corresponding Tagging rule, and pop tag.

        --push-learned-tag Add VLAN tag with learned id as the new outer tag. The default TPID value
        will be used as the new Ethertype value in the Ethernet header, the existing Ethertype of the Ethernet Header will be used
        as the Tag Ethertype field of the new tag, and the default PBITS and CFI will be used as the TCI of the new tag. If
        multiple tags are to be inserted, this treatment must be specified for each VLAN tag to be inserted.

        --create-flows <rx_vlan_ifname> <tx_vlan_ifname> Setup vlan flows for the path (rx_vlan_ifname->tx_vlan_ifname).

        --delete-flows <rx_vlan_ifname> <tx_vlan_ifname> Remove vlan flows for the path (rx_vlan_ifname->tx_vlan_ifname).

        --add-cmd <rule-id> Add cmd to the Tagging Rule whose identifier matches <rule-id> in the
        specified Tagging Rule Table. Dependencies: --if, --rx or --tx, and --tags .


```