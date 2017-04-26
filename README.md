# Kraken_db_install_scripts

Updated Kraken DB install scripts to cope with new-ish NCBI structure

Author: Mick Watson

This fork is aimed at modify the DB install scripts to use Accessions numbers
instead of GIs

## Dependencies

* [Kraken](https://github.com/DerrickWood/kraken) installed and in your $PATH
* [bioperl](http://bioperl.org)

## Usage

```shell
Kraken_db_install_scripts/kraken_scripts/download_taxonomy.sh test
# download whichever library you want with the perl scripts
# ex:
perl download_viral.pl
find library/viral/ -name '*.fna' -print0 | \
    xargs -0 -I{} -n1 Kraken_db_install_scripts/kraken_scripts/kraken-build \
    --add-to-library {} --db test

```

## License

The scripts under `kraken_scripts` are
[GPL3](kraken_shell_scripts/LICENSE.txt)  
The rest is [MIT](LICENSE.txt)
