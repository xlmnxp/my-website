<template>
    <div class="min-h-screen bg-gray-100 dark:bg-gray-900 p-8">
        <div class="container mx-auto">
            <h1 class="text-3xl font-bold text-primary dark:text-primary-dark mb-8 animate-fadeIn">Public Services</h1>

            <!-- Yggdrasil Network Section -->
            <section class="mb-12 animate-fadeIn">
                <div class="bg-white dark:bg-gray-800 rounded-lg shadow-md p-6">
                    <h2 class="text-2xl font-semibold text-primary dark:text-primary-dark mb-4">Yggdrasil Network Public
                        Peer</h2>
                    <p class="text-gray-700 dark:text-gray-300 mb-4">
                        Yggdrasil Network is a decentralized peer-to-peer network that creates an encrypted IPv6 mesh
                        network.
                        This public peer helps users connect to the Yggdrasil network and enhance its connectivity.
                    </p>

                    <div class="space-y-4">
                        <div class="bg-gray-50 dark:bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold text-primary dark:text-primary-dark mb-2">Available
                                Endpoints:</h3>
                            <div class="space-y-2">
                                <div v-for="(url, protocol) in yggEndpoints" :key="protocol"
                                    class="flex flex-col sm:flex-row sm:items-center gap-2">
                                    <span
                                        class="font-mono bg-primary/10 dark:bg-primary-dark/10 px-2 py-1 rounded text-primary dark:text-primary-dark">
                                        {{ url }}
                                    </span>
                                    <span class="text-gray-600 dark:text-gray-400">
                                        ({{ protocol }})
                                    </span>
                                </div>
                            </div>
                        </div>

                        <div
                            class="mt-4 p-4 bg-yellow-50 dark:bg-yellow-900/20 text-yellow-800 dark:text-yellow-200 rounded-lg">
                            <h4 class="font-medium mb-2">Note:</h4>
                            <ul class="list-disc list-inside space-y-1">
                                <li>The service is provided as-is without any warranties</li>
                            </ul>
                        </div>

                        <div class="bg-gray-50 dark:bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold text-primary dark:text-primary-dark mb-2">How to Connect:
                            </h3>
                            <ol class="list-decimal list-inside space-y-2 text-gray-700 dark:text-gray-300">
                                <li>Install Yggdrasil on your system</li>
                                <li>Add the peer address to your Yggdrasil configuration</li>
                                <li>Restart the Yggdrasil service</li>
                            </ol>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Bridge46 Section -->
            <section class="animate-fadeIn">
                <div class="bg-white dark:bg-gray-800 rounded-lg shadow-md p-6">
                    <h2 class="text-2xl font-semibold text-primary dark:text-primary-dark mb-4">Public Bridge46 Node
                    </h2>
                    <p class="text-gray-700 dark:text-gray-300 mb-4">
                        Bridge46 is a service that provides IPv4/IPv6 connectivity bridging. This public node helps
                        users access IPv6
                        resources from IPv4-only networks.
                    </p>

                    <div class="space-y-4">
                        <div class="bg-gray-50 dark:bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold text-primary dark:text-primary-dark mb-2">Service URL:</h3>
                            <a href="https://bridge46.sy.sa/" target="_blank" rel="noopener noreferrer"
                                class="font-mono bg-primary/10 dark:bg-primary-dark/10 px-2 py-1 rounded text-primary dark:text-primary-dark hover:underline">
                                https://bridge46.sy.sa/
                            </a>
                        </div>

                        <div
                            class="mt-4 p-4 bg-yellow-50 dark:bg-yellow-900/20 text-yellow-800 dark:text-yellow-200 rounded-lg">
                            <h4 class="font-medium mb-2">Note:</h4>
                            <ul class="list-disc list-inside space-y-1">
                                <li>The service is provided as-is without any warranties</li>
                                <li>Some websites might not work due to their security policies</li>
                                <li>HTTPS connections are supported and recommended</li>
                            </ul>
                        </div>

                        <div class="bg-gray-50 dark:bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold text-primary dark:text-primary-dark mb-2">How to Use:</h3>
                            <div class="space-y-4 text-gray-700 dark:text-gray-300">
                                <div class="space-y-2">
                                    <p>Just create a CNAME record pointing to <code
                                            class="font-mono bg-gray-200 dark:bg-gray-700 px-1 rounded">bridge46.sy.sa</code>
                                        next to your existing AAAA record in your DNS zone. Bridge46 will automatically
                                        handle the IPv4/IPv6 translation.</p>
                                </div>
                            </div>
                        </div>

                        <div class="bg-gray-50 dark:bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold text-primary dark:text-primary-dark mb-2">Features:</h3>
                            <ul class="list-disc list-inside space-y-2 text-gray-700 dark:text-gray-300">
                                <li>IPv4 to IPv6 bridging</li>
                                <li>Public access</li>
                                <li>No registration required</li>
                                <li>Supported protocols:
                                    <ul class="list-disc list-inside ml-6 mt-2 space-y-1">
                                        <li>HTTP</li>
                                        <li>HTTPS</li>
                                        <li>WebSocket (ws)</li>
                                        <li>Secure WebSocket (wss)</li>
                                        <li>Minecraft (TCP)</li>
                                    </ul>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </div>
</template>

<script setup lang="ts">
import personalInfo from 'assets/json/personal-info.json';

const yggEndpoints = {
    'TCP': 'tcp://pp1.ygg.sy.sa:8441',
    'TLS': 'tls://pp1.ygg.sy.sa:8442',
    'QUIC': 'quic://pp1.ygg.sy.sa:8443'
}

useHead({
  title: `${personalInfo.name} - Services`,
})
</script>
