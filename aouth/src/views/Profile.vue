<template>
    <div style="max-width: 600px; margin: auto; background-color: #fff; padding: 20px; border-radius: 10px; box-shadow: 0 2px 15px rgba(0,0,0,0.1);">
        <div style="display: flex; align-items: center; gap: 20px;">
            <img :src="$auth.user.picture" style="width: 80px; height: 80px; border-radius: 50%;" alt="User Profile Picture"/>
            <div>
                <h2 style="margin: 0; color: #333; font-family: 'Arial', sans-serif;">{{ $auth.user.name }}</h2>
                <h5 style="margin: 0; color: #555; font-family: 'Arial', sans-serif;">{{ $auth.user.email }}</h5>
            </div>
        </div>
        <div style="margin-top: 20px; background-color: #f8f9fa; padding: 10px; border-radius: 5px;">
            <pre style="white-space: pre-wrap; word-wrap: break-word; font-family: 'Courier New', monospace; color: #333;">{{ JSON.stringify($auth.user, null, 2) }}</pre>
        </div>
    </div>
</template>


