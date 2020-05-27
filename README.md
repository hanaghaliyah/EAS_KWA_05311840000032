# EAS_KWA_05311840000032
Nama : Hana Ghaliyah Azhar
NRP  : 05311840000032

## Login Sequel
`<b>Login</b> as admin you must. This time, the client is of no use :(. What to do?`

```
def get_user(username, password):
    database = connect_database()
    cursor = database.cursor()
    try:
        cursor.execute('SELECT username, password FROM `userandpassword` WHERE username=\'%s\' AND password=\'%s\'' % (username, hashlib.md5(password.encode())))
    except:
        return render_template("failure.html")
    row = cursor.fetchone()
    database.commit()
    database.close()
    if row is None: return None
    return (row[0],row[1])
```

## Forwarding
