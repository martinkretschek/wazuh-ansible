TASK [../roles/wazuh/wazuh-indexer : Reload systemd configuration] *****************************************************************************************************
ok: [wi2]
ok: [wi3]
FAILED - RETRYING: [wi1]: Initialize the Opensearch security index in Wazuh indexer (1 retries left).

TASK [../roles/wazuh/wazuh-indexer : Initialize the Opensearch security index in Wazuh indexer] ************************************************************************
fatal: [wi1]: FAILED! => {"attempts": 2, "changed": true, "cmd": ["sudo", "-u", "wazuh-indexer", "OPENSEARCH_PATH_CONF=/etc/wazuh-indexer", "JAVA_HOME=/usr/share/wazuh-indexer/jdk", "/usr/share/wazuh-indexer/plugins/opensearch-security/tools/securityadmin.sh", "-cd", "/etc/wazuh-indexer/opensearch-security/", "-icl", "-p", "9200", "-cd", "/etc/wazuh-indexer/opensearch-security/", "-nhnv", "-cacert", "/etc/wazuh-indexer/certs/root-ca.pem", "-cert", "/etc/wazuh-indexer/certs/admin.pem", "-key", "/etc/wazuh-indexer/certs/admin-key.pem", "-h", "172.16.21.101"], "delta": "0:00:00.529396", "end": "2024-04-24 18:23:27.941860", "msg": "non-zero return code", "rc": 255, "start": "2024-04-24 18:23:27.412464", "stderr": "", "stderr_lines": [], "stdout": "**************************************************************************\n** This tool will be deprecated in the next major release of OpenSearch **\n** https://github.com/opensearch-project/security/issues/1755           **\n**************************************************************************\nSecurity Admin v7\nWill connect to 172.16.21.101:9200\nERR: Seems there is no OpenSearch running on 172.16.21.101:9200 - Will exit", "stdout_lines": ["**************************************************************************", "** This tool will be deprecated in the next major release of OpenSearch **", "** https://github.com/opensearch-project/security/issues/1755           **", "**************************************************************************", "Security Admin v7", "Will connect to 172.16.21.101:9200", "ERR: Seems there is no OpenSearch running on 172.16.21.101:9200 - Will exit"]}

Antes foi executado ssh para os IPs com keytype para adicionar no .known_hosts do root

vmpwazi003 ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBCrNSQjq0R8cLVT5PsGX7rPEULRapftXTdQswIVsnBV/wzIKVg45QZO29w2ENJOiszY6sNNrnXP2fEzy4YGPvBM=
vmpwazi001.dcsafe.local ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIKlNnMCA+sHqzRQZa1Q4kBVKHRv3ZYAZ9+n9J8XQ5a8G
vmpwazi002.dcsafe.local ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIN0EsoD46am8soB8MrzRUAFD05JaJOsuSP67p4Ob7iaA
vmpwazi003.dcsafe.local ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIAJn66z2SaGm+EUkSzH8DzrdVq2CBPYMANmZPU9GDrvi
172.16.21.101 ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIKlNnMCA+sHqzRQZa1Q4kBVKHRv3ZYAZ9+n9J8XQ5a8G
172.16.21.102 ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIN0EsoD46am8soB8MrzRUAFD05JaJOsuSP67p4Ob7iaA
172.16.21.103 ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIAJn66z2SaGm+EUkSzH8DzrdVq2CBPYMANmZPU9GDrvi
172.16.21.105 ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIAjlFenxf+sggUha7UJ1Bbn+3ypWNM3IdOjdTg5TXapI
172.16.21.104 ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIHwsI/h5OPd6Ub6RBttft72bfTUuEzW5vvuvGy60CwLd
172.16.21.106 ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAINWqHwezyQqpjkAlRsMfgHh7vPXoXA/N0e3SHiFuNg5r
[root@vmpapro001 ~]# ssh -o HostKeyAlgorithms=ssh-ed25519 172.16.21.106



TASK [../roles/wazuh/ansible-wazuh-manager : Encode the secret] ********************************************************************************************************
skipping: [manager]

TASK [../roles/wazuh/ansible-wazuh-manager : Ensure Wazuh Manager service is started and enabled.] *********************************************************************
fatal: [manager]: FAILED! => {"changed": false, "msg": "Unable to enable service wazuh-manager: Synchronizing state of wazuh-manager.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.\nExecuting: /usr/lib/systemd/systemd-sysv-install enable wazuh-manager\nFailed to execute /usr/lib/systemd/systemd-sysv-install: No such file or directory\n"}

PLAY RECAP *************************************************************************************************************************************************************
manager                    : ok=25   changed=13   unreachable=0    failed=1    skipped=29   rescued=0    ignored=0
wi1                        : ok=33   changed=18   unreachable=0    failed=0    skipped=50   rescued=0    ignored=0
wi2                        : ok=29   changed=18   unreachable=0    failed=0    skipped=19   rescued=0    ignored=0
wi3                        : ok=29   changed=18   unreachable=0    failed=0    skipped=19   rescued=0    ignored=0


