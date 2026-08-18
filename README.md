def parse_license(data):
    parts = data.split("|")

    if len(parts) != 5:
        return None

    user = parts[0]
    hwid = parts[1]
    expire = parts[2]
    edition = parts[3]
    signature = parts[4]

    return {
        "user": user,
        "hwid": hwid,
        "expire": expire,
        "edition": edition,
        "signature": signature
    }
