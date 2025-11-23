# Cultify

Automated Cult.fit class booking via GitHub Actions.

## Overview

Cultify automatically books workout classes at your preferred Cult.fit center. The script runs daily via GitHub Actions and handles authentication using browser cookies extracted from a curl command.

## Features

- Automatic class booking at scheduled times
- Configurable time slots and workout preferences
- Smart booking (skips if already booked)
- Zero maintenance (credentials via GitHub Secrets)
- No server required (runs on GitHub Actions)

## Quick Start

1. Copy curl command from browser DevTools
2. Add as GitHub Secret named `CURL_COMMAND`
3. Push code to GitHub
4. Enable GitHub Actions

See [SETUP.md](SETUP.md) for detailed instructions.

## Configuration

Default settings:
- Workout: HRX WORKOUT
- Time slots: 7:00 AM, 8:00 AM, 9:00 AM
- Schedule: Daily at 10:05 AM UTC
- Center: 1515 (SG Palya)

Customize via environment variables:
```bash
PREFERRED_CENTER=1515
PREFERRED_SLOTS=07:00:00,08:00:00,09:00:00
PREFERRED_WORKOUT=HRX WORKOUT
```

See [CONFIG.md](CONFIG.md) for all configuration options.

## Requirements

- Active Cult.fit membership
- GitHub account
- Node.js 14+ or Bun runtime

## Local Development

```bash
# Create .env file with CURL_COMMAND
echo 'CURL_COMMAND=curl ...' > .env

# Install dependencies
bun install

# Run
bun index.js
```

## How It Works

1. Fetches available classes via Cult.fit API
2. Filters by preferred workout type and time slots
3. Checks for existing bookings
4. Books first available class matching criteria
5. Logs results

## Security

- No hardcoded credentials
- Authentication via environment variables
- GitHub Secrets for automation
- Safe to commit to public repositories

## Documentation

- [Setup Guide](SETUP.md) - Complete setup instructions
- [Configuration Guide](CONFIG.md) - Detailed configuration options
- [Configuration Summary](CONFIGURATION_SUMMARY.md) - Quick reference
- [LICENSE](LICENSE) - License information

## Contributing

Pull requests welcome for:
- Additional workout types
- Multi-center support
- Enhanced error handling
- Notification integrations

## License

MIT License - See LICENSE file for details.
