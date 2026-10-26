# SK Changkat Tualang Hub: setup guide

This folder has 3 files:

- `index.html` is the website.
- `firestore.rules` holds the database safety rules.
- `README.md` is this guide.

You need two free accounts: **Firebase** (saves scores, pupils, teachers and links) and **GitHub** (puts the site online). Use a Google account for Firebase.

## Part 1: Firebase (about 10 minutes)

1. Go to https://console.firebase.google.com and press **Create a project**. Name it, for example, `skct-hub`. Turn Google Analytics off.
2. In the left menu choose **Build > Firestore Database > Create database**.
   - Pick the closest location (for example `asia-southeast1`, Singapore).
   - Choose **Start in production mode**.
3. Still in Firestore, open the **Rules** tab. Delete everything, paste in the whole contents of `firestore.rules`, and press **Publish**.
4. Choose **Build > Authentication > Get started > Email/Password**, turn **Enable** on, and Save.
5. In Authentication open the **Users** tab and press **Add user**.
   - Email: `g-96033445@moe-dl.edu.my`
   - Password: choose a strong password. This is your admin password for the site.
   - Add no other users. Only this email is the admin.
6. Open **Project settings** (the gear icon), then **General**. Under "Your apps" press the web icon `</>`.
   - Name the app and press **Register app**. Do not tick hosting.
   - Copy the four values `apiKey`, `authDomain`, `projectId` and `appId`.
7. Open `index.html` in any text editor. Near the top of the script, replace the four `PASTE_...` values with yours. Save.

## Part 2: GitHub (about 5 minutes)

1. Sign in at https://github.com and press **New repository**. Name it, for example, `skct-hub`. Set it to **Public** and create it.
2. Press **uploading an existing file**, drag in `index.html` and `README.md`, and press **Commit changes**.
3. Open the repository **Settings > Pages**. Under "Build and deployment" choose **Deploy from a branch**, pick the `main` branch and the `/ (root)` folder, then Save.
4. After about a minute your site is live at `https://YOUR-GITHUB-NAME.github.io/skct-hub/`.

## Part 3: Allow the website to sign in (important)

In Firebase, open **Authentication > Settings > Authorized domains > Add domain**. Add `YOUR-GITHUB-NAME.github.io`, with no `https://` and no path. Without this, admin sign-in will not work.

## Using it

- Admin: press **Sign in**, choose **Admin**, and enter your email and the password from step 5.
- Teachers: choose their name and the password you set for them. You set it in the teacher sidebar with **Edit**.
- Pupils: choose their class and name.

## Good to know

- The admin password lives in Firebase, not in the website. Do not put it in `index.html`.
- Pupils and teachers do not need Google or Claude accounts.
- Pupils can still choose each other's names, because they have no passwords. This is for classroom use, not strong security.
- The free Firebase plan is plenty for one school.
