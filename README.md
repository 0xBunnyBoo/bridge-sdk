import { CanonicalBridgeSDK } from '@bnb-chain/canonical-bridge-sdk';

/**
 * Initialize SDK Instance
 * @returns SDK Instance
 */
const bridgeSDK = new CanonicalBridgeSDK({
  bridgeConfigs: [
    {
      bridgeType: 'cBridge',
      endpoint: env.CBRIDGE_ENDPOINT,
      timeout: 5000,
    },
    {
      bridgeType: 'deBridge',
      endpoint: env.DEBRIDGE_ENDPOINT,
      statsEndpoint: env.DEBRIDGE_STATS_ENDPOINT,
      timeout: 5000,
    },
  ],
});

const order = await bridgeSDK.deBridge.getOrder({
  id: '0x4cb96c88916d5f08a979750c54f3001ffb4069762326705d431a83f946b3ba64',
});
