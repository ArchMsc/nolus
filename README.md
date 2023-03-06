# Nolus-rila testnet snapshot

### Stop nolusd service and reset data:
```
sudo systemctl stop nolusd
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
rm -rf $HOME/.nolus/data
mkdir $HOME/.nolus/data
```
### Download snapshot:
```
wget -O - http://85.10.202.135/nolus/nolus-rila_latest.tar | tar xf - -C $HOME/.nolus/data
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```

### Restart service:
```
sudo systemctl restart nolusd 
```
### Check logs:
```
sudo journalctl -u nolusd -f -o cat
```
