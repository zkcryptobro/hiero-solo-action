# hedera-solo-action

A GitHub Action for setting up a Hedera Solo network. The network contains one node.
The node can be accessed at `localhost:50211`.

The action creates an account that contains 10,000,000 hbars.
All information about the account is stored as output to the github action.

## Outputs

The GitHub action outputs the following information:

- `accountId`: The account ID of the account created.
- `privateKey`: The private key of the account created.
- `publicKey`: The public key of the account created.

# Usage

```yaml
- name: Setup Hedera Solo
  uses: OpenElements/hedera-solo-action@v1
  id: solo
  
- name: Use Hedera Solo
  run: |
    echo "Account ID: ${{ steps.solo.outputs.accountId }}"
    echo "Private Key: ${{ steps.solo.outputs.privateKey }}"
    echo "Public Key: ${{ steps.solo.outputs.publicKey }}"
```

