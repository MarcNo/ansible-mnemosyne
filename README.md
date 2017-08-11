# ansible-mnemosyne

Sample script to build a KVM hypervisor on a minimal RHEL install for
my homelab

## Install RHEL 

Install a minimal RHEL 7.3 on a fresh bare metal system

## Configuring for you env

* edit hosts to put your hostname. Mine is` mnemosyne.nozell.com`

* edit the file group_vars/all/all_secret.yml and put this in it:

`RHNUSER: your-real-redhat-username`

`RHNPASSWORD: your-real-redhat-username`

* The encrypt that file

`ansible-vault encrypt group_vars/all/all_secret.yml`

* Verify your secrets were encrypted to something like:

`cat  group_vars/all/all_secret.yml `

`$ANSIBLE_VAULT;1.1;AES256`
`37316431303731316337336339636664323039656637393436343564316563663738396330636237`
`3830343161333164383738616164303737333237643633340a376463336530343833643233623230`
`62343666353530636236333430336236356237383064633937346664313632353438623831393863`
`6262663435313961360a313265373062343037616366643965373437376231386332353431316130`
`32373332383666306664666431646139333231336637393562316431373365316137353534363732`
`63333531366535666538646235333339616537653934333261643538363836316665323762323938`
`633438366231323332343233323062396261`

## Turn your bare metal into a reasonable hypervisor

`ansible-playbook -i hosts site.yml --ask-vault-pass`

## Done

For something fun to do with this new system, take a look at this: 
https://github.com/MarcNo/openshift-home-lab
