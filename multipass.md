# multipass

Create 2 VMs:
```bash
multipass launch --name vm-1
multipass launch --name vm-2
```

SSH into VM:
```bash
multipass shell vm-1
multipass shell vm-2
```

Check if VM got the IP:
```bash
multipass ls
```

Stop `vm-1`:
```bash
multipass stop vm-1
```

Restart `vm-1`:
```bash
multipass start vm-1
```

### Cleanup

Delete VMs:
```bash
multipass delete vm-1 vm-2
multipass purge
```

