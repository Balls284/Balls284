import trio
import httpx

from ignorant.modules.shopping.amazon import amazon


async def main():
    phone="2667822"
    country_code="252"
    client = httpx.AsyncClient()
    out = []

    await amazon(phone, country_code, client, out)

    print(out)
    await client.aclose()

trio.run(main)
