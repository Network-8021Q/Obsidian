
Токен при создании бэкапа VM

pbsuser@pbs!pve-token
64bb2a3e-2a10-4d35-808e-500513a3bfb9

### Шаг 1: Создадим ВМ с правильными параметрами

```bash
qm create 101 --name "FSS" \
  --memory 4096 \
  --cores 2 \
  --sockets 1 \
  --cpu host \
  --ostype win7 \
  --bios seabios \
  --machine pc-i440fx-9.2 \
  --scsihw lsi \
  --net0 e1000,bridge=vmbr0 \
  --vga cirrus
```

### Шаг 2: Импортируем диск

```bush
qm importdisk 101 /root/DB-FSS.vhdx local-lvm --format raw
```

### Шаг 3: Подключим диск как IDE

```bush
qm set 101 --ide0 local-lvm:vm-101-disk-0
qm set 101 --boot order=ide0
```

### Шаг 5: Запустим

```bush
qm start 101
```



