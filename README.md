# Geth Blacklist Functionality and Configuration

This geth file contains blacklist functionality for testnet

## Overview

The custom Geth node includes additional functionality to prevent transactions from blacklisted accounts. This functionality leverages a smart contract to determine whether a sender address is blacklisted and blocks transactions from those addresses at the transaction pool level.

## Key Features:

Blacklist Integration: Prevents transactions from accounts flagged as blacklisted in the specified smart contract.

Custom Smart Contract ABI: Enables checking the blacklist status dynamically.

## Changes

isBlacklisted Function

Checks if an account is blacklisted by interacting with a smart contract.

Returns true if the account is blacklisted; otherwise, false.

TxPool Modification

The add function now checks whether the sender is blacklisted before accepting a transaction.

If the blacklist check fails (e.g., due to network or contract issues), a warning is logged, and the transaction proceeds.
