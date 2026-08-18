from datetime import datetime

def is_expired(expire_date):
    expire = datetime.strptime(
        expire_date,
        "%Y-%m-%d"
    )

    return datetime.now() > expire


if is_expired("2026-12-31"):
    print("License Expired")
    raise SystemExit
