# immich-at-home
My tweaked configuration of Immich server to run on my UGreen DPX2800 NAS (2x4TB HDD, 2x512GB SSD). It allows Immich to use the Intel N100 iGPU at full potential for transcoding and machine learning.


## Disclosure
This repository is not the official Immich project. It only hosts my customized configuration files adapted for my specific NAS setup. The actual Immich software is the intellectual property of its original creators. Please refer to the official [Immich GitHub repository](https://github.com/immich-app/immich) for the source code, installation guides, and support.

## Deployment
1. Clone the repository into your desired folder. On my setup, this is located on the RAID 1 SSD pool at `/volume2/docker/immich`
```bash
git clone https://github.com/Sc4ndium90/immich-at-home
```

2. Configure the environment : rename the example environment file to `.env`. Open the `.env` file and add your custom password to the `DB_PASSWORD` variable. You can generate a secure password using [random.org/strings](random.org/string).

3. Check the Immich version : if it's not up to date, bump the Immich server version in the `.env` file via the `IMMICH_VERSION` variable

4. Prepare the database folder : The `./postgres` folder must exist in the current directory before launching. Create it manually or adapt the `.env` file to point to your preferred folder path.

5. Start the Immich server with `sudo docker compose up -d`.

## Updating the server
Only replace the value of `IMMICH_VERSION` to the desired Immich server version and restart the Docker Compose with `sudo docker compose up -d`.
