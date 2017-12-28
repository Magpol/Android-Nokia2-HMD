# Android-Nokia2-HMD

lk.bin extracted from NOKIA 3 firmware:
MT6737M__Unknown__Heart__Unknown__7.0__alps-mp-n0.mp1-V1.0.2_fih6737m.35.n_P96

==LK info ==
Build time:
Apr 12 2017
14:53:45

--------------------------------------------------------------------------------

** Analyzing header of lk.bin (file size is 501572) - Header is 512
				 		                      ImgSize            Name
0000000          58881688        0007a544        00006b6c        00000000
                            		   501060			         kl
0000016          00000000        00000000        00000000        00000000
0000032          00000000        00000000        ffffffff        ffffffff
0000048          58891689        00000200        00000001        00000000
0000064          00000000        00000010        00000000        00000000
0000080          ffffffff        ffffffff        ffffffff        ffffffff
*
0000512          ea000007        ea0066c4        ea0066ca        ea0066d0

** Header is using MTK struct:

#define PART_MAGIC          0x58881688
typedef union {
    struct {    
        unsigned int magic;        /* partition magic */
        unsigned int dsize;        /* partition data size */
        char         name[32];     /* partition name */
	unsigned int maddr;        /* partition memory address */
    } info;
    unsigned char data[BLK_SIZE];
} part_hdr_t;

--------------------------------------------------------------------------------

$ binwalk lk.bin 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
295844        0x483A4         Android bootimg, kernel size: 0 bytes, kernel addr: 0x5D73255B, ramdisk size: 1869570592 bytes, ramdisk addr: 0x6D692074, product name: " > page count of kernel image = %d"
377988        0x5C484         Certificate in DER format (x509 v3), header length: 4, sequence length: 945
379624        0x5CAE8         Certificate in DER format (x509 v3), header length: 4, sequence length: 945
396640        0x60D60         CRC32 polynomial table, little endian
397667        0x61163         Unix path: /openssl/crypto/bio/b_print.c
398379        0x6142B         Unix path: /openssl/crypto/asn1/a_bitstr.c
398671        0x6154F         Unix path: /openssl/crypto/asn1/ameth_lib.c
398859        0x6160B         Unix path: /openssl/crypto/asn1/tasn_dec.c
402367        0x623BF         Unix path: /openssl/crypto/lhash/lhash.c
408227        0x63AA3         Unix path: /openssl/crypto/objects/obj_dat.c
432463        0x6994F         Unix path: /openssl/crypto/objects/obj_lib.c
432695        0x69A37         Unix path: /openssl/crypto/rsa/rsa_lib.c
432855        0x69AD7         Unix path: /openssl/crypto/rsa/rsa_x931.c
433155        0x69C03         Unix path: /openssl/crypto/x509v3/v3_cpols.c
433763        0x69E63         Unix path: /openssl/crypto/x509v3/v3_crld.c
434699        0x6A20B         Unix path: /openssl/crypto/x509v3/v3_ncons.c
440984        0x6BA98         SHA256 hash constants, little endian

--------------------------------------------------------------------------------

** Extracted OEM commands from lk.bin.

sub_41e1cc6c("oem p2u", *0x41e7a3f8, 0x1, 0x0);
sub_41e1cc6c("oem LCM", *0x41e7a1e0, 0x1, 0x0);
sub_41e1cc6c("oem HALT", *0x41e7a374, 0x1, 0x0);
sub_41e1cc6c("checksum", *0x41e7a1f8, 0x1, 0x0);
sub_41e1cc6c("oem alive", *0x41e7a3f0, 0x1, 0x0);
sub_41e1cc6c("oem ForceAOS", *0x41e7a2a8, 0x1, 0x0);
sub_41e1cc6c("oem dm-verity", *0x41e7a0e0, 0x1, 0x0);
sub_41e1cc6c("oem SecureBoot", *0x41e7a160, 0x1, 0x0);
sub_41e1cc6c("oem getversions", *0x41e7a454, 0x1, 0x0);
sub_41e1cc6c("oem cert_timecount", *0x41e7a4b0, 0x1, 0x0);
sub_41e1cc6c("oem reboot-preloader", *0x41e7a4f4, 0x1, 0x0);
sub_41e1cc6c("oem getBootloaderType", *0x41e7a320, 0x1, 0x0);
sub_41e1cc6c("oem battery getcapacity", *0x41e7a23c, 0x1, 0x0);
sub_41e1cc6c("oem append-cmdline", *0x41e7a45c, 0x0, 0x0);
sub_41e1cc6c("oem test_dram", *0x41e7a1c0, 0x1, 0x0);
sub_41e1cc6c("oem unlock", *0x41e7a380, 0x1, 0x0);
sub_41e1cc6c("oem lock", *0x41e7a338, 0x1, 0x0);
sub_41e1cc6c("oem key", *0x41e7a3d0, 0x1, 0x0);
sub_41e1cc6c("oem lks", *0x41e7a2c8, 0x1, 0x0);
sub_41e1cc6c("flashing unlock", *0x41e7a380, 0x1, 0x0);
sub_41e1cc6c("flashing lock", *0x41e7a338, 0x1, 0x0);
sub_41e1cc6c("flashing get_unlock_ability", *0x41e7a16c, 0x1, 0x0);
