import hashlib

def sha256_file(path):
    h = hashlib.sha256()

    with open(path, "rb") as f:
        while True:
            data = f.read(1024 * 1024)
            if not data: 
                break
            h.update(data)

    return h.hexdigest()


original = "YOUR_ORIGINAL_HASH"
current = sha256_file("mytool.exe")

if current != original:
    print("File modified!")
    raise SystemExit

print("File OK")
